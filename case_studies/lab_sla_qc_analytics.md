# Lab SLA & QC Analytics (SQL)

## TL;DR
- Standardized result-level SLA math and rolled it up by shift/site/analyte.
- Quantified QC-related delays by comparing turnaround time (TAT) near QC failures vs normal operation.
- Produced reproducible SQL views + a notebook-driven report with saved visuals.

## Business Question
Where are SLA misses happening (shift, site, analyte), and what operational signals (QC proximity, intake surges) explain those misses?

## Data
- Source: Synthetic lab operations seed described in the project repo.
- Notes: The repo explicitly notes reseeding can change exact values; insights/actions are intended to hold.

## Approach
- Define SLA at the **result level** using time logic:
  - `SLA % = 100 × AVG( (verified_ts − received_ts) ≤ analyte.tat_target_minutes )`
- Build canonical SQL views for reuse (e.g., SLA by shift/site; QC proximity impact; rolling 6-hr intake).
- Use percentiles (p95) alongside averages to spot tail-risk vs SLA targets.
- Convert insights into operational actions (load balancing, QC scheduling guardrails, intake lane design).

## Key Results (verified)
From the project README TL;DR table:
- **Shift SLA:** Night ~100.0%, Evening ~99.1%, Day ~91.8% (Day is the bottleneck under peak intake).
- **Site SLA:** Clinics ~98–100%; ED ~93.9% (ED drags the overall average).
- **QC proximity impact:** Avg TAT 34.6 min (normal) vs 73.8 min (near QC fail) → **+39.2 min / +113%**.

Source: https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis#tldr-key-results

## So What (Decision / Impact)
- This is the “ops analytics” pattern I use in healthcare domains: define audit-ready metrics first, then build repeatable rollups that connect directly to actions.
- Demonstrates how to isolate an operational driver (QC) and quantify its effect size on throughput (TAT), not just describe it.

## Artifacts
- Repo: https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis
- README + visuals index: https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis#visuals
- How to verify:
  - Create the database, run the seed + views SQL, then run the notebook per the repo “Run it” section.

## Tech + Skills Demonstrated
- SQL (PostgreSQL): time logic, window functions, percentiles, reusable views
- Ops analytics: SLA/TAT definitions, bottleneck diagnosis, action mapping
- Reproducibility: seeded data + canonical queries + notebook report
