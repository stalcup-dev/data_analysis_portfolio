# Lab SLA & QC Analytics

![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-Jupyter-F7CA18?style=flat&logo=jupyter&logoColor=white)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_Analytics-00AEEF?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-4CAF50?style=flat)

> **What I built:** A production-style SQL analytics pipeline that standardizes SLA measurement across a reference lab's shifts, sites, and analytes — then isolates quality control failures as a quantifiable throughput driver.

---

## The Problem

Lab operations managers at reference labs often have a gut sense that *something* causes delays — but not the data to prove it, prioritize it, or act on it. Common symptoms:

- SLA targets are tracked manually or inconsistently across analytes
- QC failures are logged but their downstream TAT impact is never measured
- Intake surge windows are handled reactively instead of planned around

**This project answers:** *Where are SLA misses happening, and what operational signals explain them?*

---

## Key Results at a Glance

| Signal | Finding | So What |
|---|---|---|
| **Day-shift SLA** | **91.8%** vs Evening 99.1% / Night ~100% | Day is the constraint — it has both the most volume and the weakest SLA |
| **ED site SLA** | **93.9%** vs Clinics 98–100% | ED drags the overall average; needs dedicated throughput intervention |
| **QC proximity impact** | **34.6 min** (normal) → **73.8 min** (near QC fail) | A nearby QC failure **doubles** average TAT (+39.2 min, +113%) |
| **Analyte risk** | CBC/PTINR on Day-shift shows the weakest p95 margin | Highest-volume analytes at peak hours = tightest SLA exposure |

> Numbers reflect a synthetic seed; reseeding may shift exact values — insights and actions are designed to hold.

---

## Visuals

### SLA by Shift & Site

<table>
<tr>
<td width="50%">

**Shift SLA — Day is the bottleneck**

![SLA by Shift](https://raw.githubusercontent.com/stalcup-dev/sql-lab-insights-and-sla-analysis/main/visuals/fig_sla_by_shift.png)

Day-shift carries the highest intake volume *and* the lowest SLA rate. Evening and Night operate near-perfectly — not because they're better staffed, but because volume pressure is lower.

</td>
<td width="50%">

**Site SLA — ED is the outlier**

![SLA by Site](https://raw.githubusercontent.com/stalcup-dev/sql-lab-insights-and-sla-analysis/main/visuals/fig_sla_by_site.png)

All clinics hit 98–100% SLA. The Emergency Department is the single outlier at 93.9%, driven by specimen mix complexity and unpredictable arrival timing.

</td>
</tr>
</table>

---

### QC Failure Impact on Turnaround Time

![QC Impact on TAT](https://raw.githubusercontent.com/stalcup-dev/sql-lab-insights-and-sla-analysis/main/visuals/fig_qc_fail_impact.png)

This is the headline finding. A QC failure on the same bench within 60 minutes of a result more than **doubles** average TAT — from 34.6 to 73.8 minutes. The mechanism is straightforward: QC failures trigger hold/repeat/re-run workflows that block the bench. The insight is that this effect is *measurable and schedulable* — QC windows can be moved away from peak intake.

---

### Rolling 6-Hour Intake Surge

![Rolling 6-hr Intake](https://raw.githubusercontent.com/stalcup-dev/sql-lab-insights-and-sla-analysis/main/visuals/fig_rolling_6hr.png)

The intake curve shows a clear afternoon-to-evening surge. This overlaps with the end of Day shift and the start of Evening — creating a handoff window under maximum load. This is where load balancing and courier staggering have the highest leverage.

---

### SLA Heatmap — Analyte × Shift

![SLA Heatmap by Analyte × Shift](https://raw.githubusercontent.com/stalcup-dev/sql-lab-insights-and-sla-analysis/main/visuals/fig_sla_heatmap_analyte_shift.png)

The heatmap cross-cuts every analyte against every shift. **CBC and PTINR on Day-shift** are the weakest cells — exactly where volume peaks. This tells you *precisely* where to focus automation, load-balancing, or staffing decisions.

---

### TAT Percentiles by Analyte

![TAT Percentiles by Analyte](https://raw.githubusercontent.com/stalcup-dev/sql-lab-insights-and-sla-analysis/main/visuals/tat_percentiles_by_analyte.png)

Averages can hide tail risk. This chart compares p50 vs p95 TAT against each analyte's SLA target. All analytes clear their targets at the median — but p95 margins are thinnest for Day-shift CBC/PTINR, confirming where operational buffer is most at risk.

---

## Analytical Approach

### 1. Define SLA at the result level

Most lab SLA tracking aggregates too early and loses the signal. This analysis defines SLA at the individual result:

```sql
SLA % = 100 × AVG( (verified_ts − received_ts) ≤ analyte.tat_target_minutes )
```

Each result either hits SLA or it doesn't — then roll up by whatever slice is relevant (shift, site, analyte, time window).

### 2. Build reusable canonical views

Rather than ad hoc queries, the analysis ships canonical SQL views that any downstream report can join:

- `synth.sla_shift_v` — SLA + TAT stats by shift
- `synth.sla_site_v` — SLA + TAT stats by site
- `synth.qc_proximity_v` — TAT comparison near vs far from QC failures
- Rolling intake CTEs for time-windowed load analysis

### 3. Measure tail risk with percentiles

Averages tell you whether you're usually on time. **p95 tells you your worst-case operational exposure.** Both metrics are included so a manager can see not just the average but where SLA starts to break down under stress.

### 4. Isolate QC as a causal driver

The QC proximity query uses a correlated subquery to flag each result as "near a QC fail" (same bench, within 60 minutes prior). This produces a clean A/B comparison:

```sql
EXISTS (
  SELECT 1 FROM synth.qc_events q
  WHERE q.bench = a.bench
    AND q.severity = 'fail'
    AND q.event_ts BETWEEN r.verified_ts - INTERVAL '60 minutes'
                       AND r.verified_ts
) AS near_fail
```

The result is a number (+39.2 min) that leadership can act on — not just a qualitative observation.

---

## SQL Spotlight

<details>
<summary><b>SLA by Shift — result-level rollup</b></summary>

```sql
-- Inputs : synth.results, synth.specimens, synth.analytes
-- Outputs: shift, avg_tat_min, sla_hit_pct, n

WITH m AS (
  SELECT
      CASE
        WHEN EXTRACT(HOUR FROM s.received_ts) BETWEEN  7 AND 14 THEN 'Day'
        WHEN EXTRACT(HOUR FROM s.received_ts) BETWEEN 15 AND 22 THEN 'Evening'
        ELSE 'Night'
      END AS shift,
      EXTRACT(EPOCH FROM (r.verified_ts - s.received_ts)) / 60.0 AS tat_min,
      a.tat_target_minutes AS sla_min
  FROM synth.results   r
  JOIN synth.specimens s USING (specimen_id)
  JOIN synth.analytes  a USING (analyte_code)
)
SELECT
    shift,
    ROUND(AVG(tat_min), 1)                           AS avg_tat_min,
    ROUND(100.0 * AVG((tat_min <= sla_min)::int), 2) AS sla_hit_pct,
    COUNT(*)                                         AS n
FROM m
GROUP BY shift
ORDER BY sla_hit_pct DESC;
```
</details>

<details>
<summary><b>QC Fail Proximity Impact — TAT comparison</b></summary>

```sql
-- Inputs : synth.results, synth.specimens, synth.analytes, synth.qc_events
-- Window : 60 minutes before verification, same bench

WITH j AS (
  SELECT
      EXTRACT(EPOCH FROM (r.verified_ts - s.received_ts)) / 60.0 AS tat_min,
      EXISTS (
        SELECT 1 FROM synth.qc_events q
        WHERE q.bench    = a.bench
          AND q.severity = 'fail'
          AND q.event_ts BETWEEN r.verified_ts - INTERVAL '60 minutes'
                             AND r.verified_ts
      ) AS near_fail
  FROM synth.results   r
  JOIN synth.specimens s USING (specimen_id)
  JOIN synth.analytes  a USING (analyte_code)
)
SELECT
    near_fail,
    ROUND(AVG(tat_min), 1) AS avg_tat,
    COUNT(*)               AS n
FROM j
GROUP BY near_fail
ORDER BY near_fail;
```
</details>

<details>
<summary><b>Rolling 6-Hour Intake — staffing curve</b></summary>

```sql
-- Inputs : synth.specimens
-- Outputs: hr (hour bucket), received_count, rolling_6hr_total

WITH timeline AS (
  SELECT generate_series(
           date_trunc('hour', MIN(received_ts)),
           date_trunc('hour', MAX(received_ts)),
           INTERVAL '1 hour'
         ) AS hr
  FROM synth.specimens
),
counts AS (
  SELECT t.hr, COUNT(*) AS received_count
  FROM timeline t
  JOIN synth.specimens s
    ON s.received_ts >= t.hr
   AND s.received_ts <  t.hr + INTERVAL '1 hour'
  GROUP BY t.hr
)
SELECT
    hr,
    received_count,
    SUM(received_count)
      OVER (ORDER BY hr ROWS BETWEEN 5 PRECEDING AND CURRENT ROW)
      AS rolling_6hr_total
FROM counts
ORDER BY hr;
```
</details>

---

## Insights → Actions

This is where analytics earns its keep — not in the charts, but in what changes after them.

| Finding | Recommended Action |
|---|---|
| **Day-shift is the constraint** (91.8% SLA, highest volume) | Pre-batch routine **CBC/PTINR** before the Day peak; load-shift to Evening/Night where capacity exists |
| **ED drives site SLA down** (93.9%) | Stagger ED courier drops; create dedicated pre-accession / STAT lanes during identified surge windows |
| **QC proximity adds +39 min** to TAT | Schedule QC and maintenance *outside* peak intake bands; enforce guardrails that prevent QC from running at high-load hours |
| **CBC/PTINR on Day** = weakest SLA margin | Prioritize auto-verify expansion for low-risk Day results where policy permits |

---

## Why This Matters to Ops & Quality Teams

This project demonstrates the **ops analytics pattern** I apply in healthcare settings:

1. **Audit-ready metric definition** — SLA is defined at the result level with a reproducible formula, not a narrative
2. **Effect size, not just description** — QC proximity doesn't "seem to cause delays"; it adds **+39.2 minutes** on average
3. **Actionable segmentation** — findings point to specific shifts, sites, and analytes rather than vague "process improvements"
4. **Reproducible infrastructure** — canonical SQL views mean the next analyst can build on this work, not re-derive it

---

## Tech & Skills Demonstrated

| Category | Details |
|---|---|
| **SQL (PostgreSQL)** | Time arithmetic, correlated subqueries, window functions (`SUM OVER`), percentiles (`PERCENTILE_CONT`), `generate_series`, reusable views |
| **Analytics patterns** | SLA/TAT definition, bottleneck isolation, effect-size quantification, tail-risk analysis (p95) |
| **Healthcare ops domain** | Lab workflows, QC event impact, shift-based capacity patterns, site-level variability |
| **Reproducibility** | Seeded synthetic data + canonical views + notebook-driven report with saved visuals |
| **Python / Jupyter** | Matplotlib charting, `psycopg2` DB connectivity, notebook-as-report pattern |

---

## Artifacts

| Resource | Link |
|---|---|
| 📁 Full repository | [sql-lab-insights-and-sla-analysis](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis) |
| 📊 Visuals index | [README → Visuals](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis#visuals) |
| 📓 Notebook report | [`01_SLA_Analyst_Report.ipynb`](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis/blob/main/01_SLA_Analyst_Report.ipynb) |

**To reproduce:** create the database, run `sql/01–04` in order, configure `.env`, then run the notebook. All outputs save to `visuals/`.
