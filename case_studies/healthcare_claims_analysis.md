# 🏥 Healthcare Claims Analysis

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white)
![matplotlib](https://img.shields.io/badge/matplotlib-Visualization-11557C?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-Healthcare%20Analytics-00AEEF?style=for-the-badge)
![Pipeline](https://img.shields.io/badge/Pipeline-Reproducible-brightgreen?style=for-the-badge)

**End-to-end Python analytics pipeline · Auto-generated documentation · Audit-ready outputs**

[📋 Decision Memo](https://github.com/stalcup-dev/healthcare-claims-analysis/blob/main/docs/decision_memo.md) · [📁 Full Repository](https://github.com/stalcup-dev/healthcare-claims-analysis)

</div>

---

## The Problem

Revenue cycle analysts and finance operations leads face a recurring challenge: **claims data is large, messy, and full of manual handoff risk**. Reports go stale. Numbers get re-typed. Definitions drift. When a stakeholder asks "how was this computed?" — nobody has a clean answer.

This project answers that challenge with a **production-style analytics pipeline** that:
- Validates data quality before any metric is computed
- Derives every figure programmatically — no hand-typed numbers, anywhere
- Renders decision-ready documentation directly from pipeline outputs

> 🎯 **Core question:** What are the headline claims KPIs, cost concentration signals, and "where to look next" insights we can surface in a reproducible, audit-ready decision memo?

---

## Key Results at a Glance

| Metric | Value |
|---|---|
| 📦 Total Claims | 1,000 |
| 💵 Total Billed | **$297,191.00** |
| 📊 Average Claim | $297.19 |
| 📈 P95 Claim | $480.00 |
| 🧬 Unique Diagnoses | 100 |
| 🏆 Top Diagnosis | A05.4 — $5,872 (1.98% of spend) |
| 📅 Date Range | May 2024 – Sep 2024 |

### Cost Concentration (Pareto)

| Patient Tier | % of Total Cost |
|---|---|
| Top 1% | 1.68% |
| Top 5% | 8.25% |
| Top 10% | **16.12%** |

> 💡 **Insight:** The top 10% of patients drive 16% of total spend. Targeted care management for this cohort represents the highest-ROI intervention opportunity.

---

## Visual Evidence

### 📉 Cost Concentration — Pareto Curve
*Top 10% of patients account for 16.1% of total spend. Targeting this cohort maximizes intervention ROI.*

![Pareto Analysis](https://raw.githubusercontent.com/stalcup-dev/healthcare-claims-analysis/main/outputs/figures/pareto.png)

---

### 📅 Monthly Billing Trend
*Total billed amounts over the analysis window (May–September 2024). Useful baseline for detecting future anomalies or volume shifts.*

![Monthly Trend](https://raw.githubusercontent.com/stalcup-dev/healthcare-claims-analysis/main/outputs/figures/monthly_trend.png)

---

### 🧬 Top Diagnoses by Total Billed
*A05.4 leads all ICD codes in total spend — the primary clinical target for cost management programs.*

![Top Diagnoses](https://raw.githubusercontent.com/stalcup-dev/healthcare-claims-analysis/main/outputs/figures/top5_diagnoses_total_billed.png)

---

### 📊 Claim Amount Distribution
*Distribution of individual claim values. Low skew in this synthetic dataset; real-world claims typically show a long right tail.*

![Claim Distribution](https://raw.githubusercontent.com/stalcup-dev/healthcare-claims-analysis/main/outputs/figures/claim_amount_distribution.png)

---

### 📦 Patient Total Cost — Box Plot
*Per-patient cost spread. Outlier thresholds (z ≥ 3.0) used to flag high-cost individuals for case management review.*

![Patient Cost Boxplot](https://raw.githubusercontent.com/stalcup-dev/healthcare-claims-analysis/main/outputs/figures/patient_total_cost_boxplot.png)

---

## How It Works — Pipeline Architecture

```
claim_data.csv
      │
      ▼
[Quality Checks]  ──  src/claims/quality.py
      │                (missingness, ranges, uniqueness)
      ▼
[Clean & Enrich]  ──  scripts/run_all.py
      │
      ▼
[Metrics & KPIs]  ──  src/claims/metrics.py
      │                (KPIs, Pareto, anomalies, trends)
      ▼
[Render Outputs]  ──  scripts/render_*.py
      │                (auto-generated docs — no manual edits)
      ▼
outputs/  +  docs/
```

Three design principles drove every decision:

| Principle | What it means in practice |
|---|---|
| 🔁 **Reproducible** | Every number in every doc traces back to a pipeline output — re-run to refresh everything |
| 🧩 **Modular** | Quality checks, metrics, and rendering are independently testable components |
| 🔍 **Auditable** | No hardcoded values anywhere; all assumptions documented in the data dictionary |

---

## Approach & Methodology

### 1. Ingestion & Quality Checks
Before computing a single metric, the pipeline validates:
- **Missingness** — flags columns exceeding acceptable null thresholds
- **Range checks** — ensures claim amounts, dates, and codes fall within valid bounds
- **Uniqueness** — confirms patient/claim IDs are as expected

This step makes outputs **audit-ready** — stakeholders can trust the numbers because the data was validated before analysis began.

### 2. KPI Computation
Core metrics include total billed, per-claim averages, P95/median distributions, and PMPM. All values are written to `outputs/tables/` as CSVs — the single source of truth for all downstream documents.

### 3. Cost Concentration (Pareto)
Patients are ranked by total spend and bucketed into tiers (top 1%, 5%, 10%). The Pareto curve visualizes how cost concentrates in a small fraction of the population — a standard technique in population health management.

### 4. Anomaly Detection
Patients with a z-score ≥ 3.0 on total cost are flagged for case management review. In this synthetic dataset, no outliers were detected — real-world claims typically surface 2–5% of patients in this tier.

### 5. Auto-Generated Documentation
The decision memo and data dictionary are rendered programmatically from pipeline outputs. This eliminates transcription errors and means **documentation stays in sync with the data automatically**.

---

## So What — Business Impact

**Pareto opportunity:**
The top 10% of patients represent 16.1% of spend. Disease management or care coordination targeting this cohort could yield meaningful cost reduction with a relatively narrow intervention scope.

**Clinical focus:**
Diagnosis A05.4 is the leading cost driver. A targeted prevention or condition management program — educational materials, screening protocols, claim frequency tracking — is the highest-impact clinical lever available with this dataset.

**Operational value:**
The pipeline itself is the deliverable. Because every output is reproducible and every metric is defined in the data dictionary, a new analyst can onboard, re-run the pipeline, and trust the results immediately — no institutional knowledge required.

### Recommended Actions

1. **Segment patients** into utilization tiers (top 1%, 5%, 10%) and pilot care management interventions with the highest tier first.
2. **Focus on A05.4** — analyze root causes, develop educational materials, and establish improvement metrics (claim frequency, severity trend, month-over-month delta).
3. **Establish monitoring dashboards** to track cost concentration, anomaly flags, and top diagnoses on a rolling monthly cadence.

---

## Limitations & Risks

| Limitation | Impact | Mitigation |
|---|---|---|
| **Synthetic data** | Patterns may not reflect real distributions | Validate against actual claims before acting |
| **Temporal scope** | Fixed window; seasonal trends not visible | Implement rolling monthly re-analysis |
| **Missing context** | No clinical outcomes, demographics, or provider data | Layer in additional data sources for richer segmentation |

---

## Reproduce This Analysis

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run the full pipeline end-to-end
python -m scripts.run_all
```

**Pipeline outputs:**

| Output | Location |
|---|---|
| Clean dataset | `outputs/data/claims_clean.csv` |
| KPI & analysis tables | `outputs/tables/*.csv` |
| Figures | `outputs/figures/*.png` |
| Decision memo | `docs/decision_memo.md` |
| Data dictionary | `docs/data_dictionary.md` |

---

## Artifacts & Further Reading

| Resource | Link |
|---|---|
| 📁 Full Repository | [healthcare-claims-analysis](https://github.com/stalcup-dev/healthcare-claims-analysis) |
| 📋 Decision Memo | [docs/decision_memo.md](https://github.com/stalcup-dev/healthcare-claims-analysis/blob/main/docs/decision_memo.md) |
| 📖 Data Dictionary | [docs/data_dictionary.md](https://github.com/stalcup-dev/healthcare-claims-analysis/blob/main/docs/data_dictionary.md) |
| 📓 Exploratory Notebook | [Healthcare_Claims_Analysis.ipynb](https://github.com/stalcup-dev/healthcare-claims-analysis/blob/main/Healthcare_Claims_Analysis.ipynb) |

---

## Skills Demonstrated

```
Data Engineering       ████████████░░  Pipeline design, modular architecture, reproducibility
Data Quality           ███████████░░░  Ingestion checks, audit-ready metric definitions
Analytics              ████████████░░  KPIs, Pareto analysis, anomaly detection, trend analysis
Visualization          ██████████░░░░  matplotlib charts (distribution, Pareto, trends, box plots)
Documentation          █████████████░  Auto-generated decision memo + data dictionary
Python                 ████████████░░  pandas, numpy, matplotlib, modular scripting
```

> 💼 **For recruiters:** This project was designed to mirror production analytics workflows — not just an analysis, but an analytics *product*. The emphasis on reproducibility, auditability, and auto-generated documentation reflects how I think about delivering analytical work in team and stakeholder environments.
