# Allen Stalcup — Data Analyst Portfolio

## Recruiter 60-second scan

I’m targeting **remote RevOps Analyst, Revenue Cycle Analyst, and RCM Analyst** roles (plus Data Analyst / BI roles with revenue ownership).

I build **decision-ready analytics** with reproducible workflows: clear business question → validated analysis → stakeholder-facing recommendation.

### Start here (fastest way to evaluate fit)
- **Revenue Cycle / RCM analytics focus:** [Revenue Cycle Healthcare Claims](case_studies/revenue_cycle_healthcare_claims.md) → [Healthcare Claims Analysis](case_studies/healthcare_claims_analysis.md) → [Cohort Retention Decision Pack](case_studies/cohort_retention_decision_pack.md)
- **Decision quality under uncertainty:** [A/B Marketing Experiment — Ad vs PSA](case_studies/ab_marketing_experiment.md)
- **End-to-end delivery (data model → forecast → BI):** [Sales Forecasting & KPI Dashboard](case_studies/sales_forecasting_kpi_dashboard.md)

### What this portfolio demonstrates
- I scope ambiguous business questions into measurable KPIs and explicit decision criteria.
- I pair analysis with QA guardrails (validation checks, assumptions, and caveats) before recommendations.
- I deliver stakeholder-facing outputs (decision packs, case studies, and KPI-ready summaries), not just notebooks.

**Top proof of work (healthcare + RevOps priority)**
- **Revenue cycle claims analytics:** denial and AR performance signals mapped to workflow fixes. ([Repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims) | [Case study](case_studies/revenue_cycle_healthcare_claims.md))
- **Healthcare claims KPI concentration analysis:** cost concentration and KPI memoing for prioritization. ([Repo](https://github.com/stalcup-dev/healthcare-claims-analysis) | [Case study](case_studies/healthcare_claims_analysis.md))
- **Medicaid spending open analysis:** national Medicaid spending trends and cost drivers translated into clear follow-up priorities. ([Repo](https://github.com/stalcup-dev/medicaid-spending-open-analysis))
- **Cohort retention decision pack:** activation/retention cohort diagnostics tied to RevOps prioritization. ([Repo](https://github.com/stalcup-dev/cohort-retention-decision-pack) | [Case study](case_studies/cohort_retention_decision_pack.md))
- **Steam decision pack:** market, pricing, and launch-timing signals turned into a ship-ready recommendation memo. ([Repo](https://github.com/stalcup-dev/steam-decision-pack) | [Case study](case_studies/steam_decision_pack.md))
- **A/B experiment (ship/no-ship decision):** SRM checks, lift analysis, and decision memo. ([Repo](https://github.com/stalcup-dev/marketing-ab-experiment) | [Decision pack](https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports))
- **Forecasting + BI delivery:** ETL → forecasting → KPI dashboard pipeline. ([Repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl) | [Dashboard image](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png))
- **Healthcare operations SQL analytics:** SLA/TAT bottlenecks and operational recommendations. ([Repo](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis) | [Key results](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis#tldr-key-results))

**Selected measurable outcomes**
- Forecasting pipeline: **median MAPE ~12.3%**, **~80% interval coverage**, and near-zero holdout bias.
- Lab operations analytics: QC-proximate windows showed **+39.2 minutes TAT (+113%)** versus normal periods.
- Claims KPI concentration analysis: **top 10% of patients account for 16.12% of billed cost** in the portfolio dataset.
- Automated KPI reporting eliminated a recurring **~4 hours/week of manual reporting** in the forecasting project.
- A/B decision pack detected **SRM risk** and prevented a potentially invalid “ship” call before rerandomization.
- Revenue-cycle and cohort projects now include an explicit **impact-quantification plan** (baseline, formula, and 30/60/90-day tracking design).

### Role fit: RevOps / RCM
- KPI design for revenue workflows: denial rate, AR aging, concentration, throughput, and SLA/TAT.
- Root-cause segmentation by payer/provider/process step to support prioritization.
- Decision memos and stakeholder summaries that connect analytics to operational actions.

### Quantified impact playbook (how I address the “directional vs delta” gap)
For projects where production post-implementation outcomes are not yet available, I now include a standard quantification block:
1. **Baseline**: current metric level + period (e.g., denial rate over trailing 8 weeks).
2. **Effect estimate**: expected point estimate + confidence band from analysis or benchmark.
3. **Business translation**: convert effect into dollars/hours/cycle-time with explicit assumptions.
4. **Decision threshold**: define what effect size justifies ship/scale/no-ship.
5. **30/60/90 follow-up**: pre-committed check-in metrics to validate realized impact vs estimate.

This format is now documented in case studies so hiring teams can see both analytical findings and implementation-grade impact math.

---

## Case studies (best starting point)

- [A/B Marketing Experiment — Ad vs PSA](case_studies/ab_marketing_experiment.md)
- [Steam Decision Pack](case_studies/steam_decision_pack.md)
- [Sales Forecasting & KPI Dashboard (Vita Markets)](case_studies/sales_forecasting_kpi_dashboard.md)
- [Lab SLA & QC Analytics (SQL)](case_studies/lab_sla_qc_analytics.md)
- [Healthcare Claims Analysis](case_studies/healthcare_claims_analysis.md)
- [Revenue Cycle Healthcare Claims — Denials & AR Focus](case_studies/revenue_cycle_healthcare_claims.md)
- [Cohort Retention Decision Pack](case_studies/cohort_retention_decision_pack.md)
- [GSS Happiness — Adjusted Effects (Survey Inference)](case_studies/gss_happiness_adjusted_effects.md)
- [Stack Overflow 2024 Developer Survey — Tech Trends](case_studies/stack_overflow_2024_trends.md)

| Case Study | Domain | Outcome highlight |
| --- | --- | --- |
| A/B Marketing Experiment — Ad vs PSA | Experimentation | Lift analysis + no-ship decision memo |
| Steam Decision Pack | Gaming market analytics | Pricing and launch recommendation memo |
| Sales Forecasting & KPI Dashboard | E-commerce / Forecasting | Forecast performance + dashboard delivery |
| Lab SLA & QC Analytics | Healthcare operations | Bottleneck diagnosis and SLA improvement plan |
| Healthcare Claims Analysis | Healthcare analytics | KPI summary + concentration signals |
| Revenue Cycle Healthcare Claims | Healthcare revenue cycle | Denial + AR prioritization workflow |
| Cohort Retention Decision Pack | RevOps / Growth analytics | Activation + retention-driven prioritization |
| GSS Happiness — Adjusted Effects | Survey inference | Adjusted effects with inference guardrails |
| Stack Overflow 2024 Trends | Survey analytics | Stakeholder-ready trend synthesis |

---

## Core skills (with evidence)

| Skill | What I can do | Evidence |
|---|---|---|
| RevOps / RCM analytics | Denial trends, AR drivers, KPI monitoring, and prioritization playbooks | [Revenue cycle case study](case_studies/revenue_cycle_healthcare_claims.md) |
| Cohort retention analytics | Cohort construction, activation/retention diagnostics, and action prioritization | [Cohort retention case study](case_studies/cohort_retention_decision_pack.md) |
| Experimentation & inference | Effect sizes, CIs, SRM checks, practical decision framing | [Marketing A/B decision pack](https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports) |
| Market sizing & decision packs | Competitive benchmarking, pricing bands, and recommendation memos | [Steam decision pack case study](case_studies/steam_decision_pack.md) |
| SQL analytics | CTEs, time logic, KPI definitions, percentile/TAT analysis | [Lab SLA SQL project](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis) |
| Forecasting & KPI pipelines | Model performance validation + business KPI outputs | [Sales forecasting repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl) |
| BI storytelling | Dashboard-first communication for business users | [KPI dashboard image](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png) |

**Tech stack:** Python, SQL (PostgreSQL), dbt, Power BI (DAX), Tableau, Git/GitHub

---

## How to scan featured projects
Each snapshot uses the same structure (**business question → approach → result**) so you can quickly evaluate problem framing, analytical rigor, and decision usefulness.

---

## Featured project snapshots

### 1) Revenue Cycle Healthcare Claims
**Business question:** Which denial and AR drivers should be prioritized first to reduce rework and leakage?

**Approach:** Denial segmentation by payer/provider + AR aging workflow diagnostics.

**Result:** Mapped top denial/AR drivers to concrete front-end and follow-up playbooks.

**Links:** [Repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims) · [Case study](case_studies/revenue_cycle_healthcare_claims.md)

### 2) Healthcare Claims Analysis
**Business question:** Which claims KPIs and concentration signals should leadership review first?

**Approach:** Reproducible Python pipeline with QA checks, KPI computation, and memo-ready outputs.

**Result:** Produced concentration and KPI summaries for faster cost/effort prioritization.

**Links:** [Repo](https://github.com/stalcup-dev/healthcare-claims-analysis) · [Case study](case_studies/healthcare_claims_analysis.md)

### 3) Medicaid Spending Open Analysis
**Business question:** Where is Medicaid spending growing fastest nationally, and which cost drivers should be reviewed first?

**Approach:** Built a reproducible open-data workflow to track national spending trends, break down spending composition, and summarize key shifts in a decision-ready format.

**Result:** Delivered a concise national spending review that surfaces the biggest trend changes and turns them into actionable next-step priorities.

**Links:** [Repo](https://github.com/stalcup-dev/medicaid-spending-open-analysis)

### 4) Cohort Retention Decision Pack
**Business question:** Which lifecycle stages are driving retention drop-off, and where should RevOps focus first?

**Approach:** Cohort-based activation and retention analysis with segment-level diagnostics and prioritization framing.

**Result:** Identified the highest-impact retention gaps and translated findings into a focused action plan for follow-up experiments.

**Links:** [Repo](https://github.com/stalcup-dev/cohort-retention-decision-pack) · [Case study](case_studies/cohort_retention_decision_pack.md)

### 5) Steam Decision Pack
**Business question:** Which release/pricing strategy should be prioritized for a Steam launch decision?

**Approach:** Product and competitor segmentation, price-band benchmarking, and recommendation framing in a decision-pack format.

**Result:** Produced a concise recommendation memo with assumptions, risks, and next-step validation checks.

**Links:** [Repo](https://github.com/stalcup-dev/steam-decision-pack) · [Case study](case_studies/steam_decision_pack.md)

### 6) A/B Marketing Experiment — Ad vs PSA
**Business question:** Should we ship ad creative based on measured lift?

**Approach:** Data QA + SRM checks, hypothesis testing, confidence intervals, practical-significance framing.

**Result:** Detected randomization risk (SRM) and recommended **no-ship** until rerun with clean assignment.

**Links:** [Repo](https://github.com/stalcup-dev/marketing-ab-experiment) · [Decision pack](https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports)

### 7) Sales Forecasting & KPI Dashboard (ETL + BI)
**Business question:** Can raw sales data become refreshable planning KPIs + reliable forecasts?

**Approach:** PostgreSQL + dbt modeling → Python forecasting pipeline → Power BI reporting.

**Result:** Reported holdout performance (median MAPE ~12.3%, ~80% coverage) and delivered a repeatable KPI workflow.

**Links:** [Repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl) · [KPI dashboard](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png)

### 8) Lab SLA & QC Analytics (SQL)
**Business question:** Where are SLA misses concentrated, and what operational actions reduce delay risk?

**Approach:** Shift/site/analyte segmentation, p95 TAT analysis, QC-proximity impact checks.

**Result:** Isolated day-shift and ED bottlenecks and identified QC-adjacent periods as major risk multipliers.

**Links:** [Repo](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis) · [Case study](case_studies/lab_sla_qc_analytics.md)

---

## Full project catalog

### Healthcare, RevOps & operations
- Revenue Cycle Healthcare Claims: https://github.com/stalcup-dev/revenue-cycle-healthcare-claims
- Healthcare Claims Analysis: https://github.com/stalcup-dev/healthcare-claims-analysis
- Medicaid Spending Open Analysis: https://github.com/stalcup-dev/medicaid-spending-open-analysis
- Cohort Retention Decision Pack: https://github.com/stalcup-dev/cohort-retention-decision-pack
- SQL Lab Insights & SLA Analysis: https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis
- Chemistry QC Automation & Westgard Rules: https://github.com/stalcup-dev/chemistry-qc-automation

### Experimentation
- A/B Marketing Experiment — Ad vs PSA: https://github.com/stalcup-dev/marketing-ab-experiment

### Market analytics
- Steam Decision Pack: https://github.com/stalcup-dev/steam-decision-pack

### E-commerce & forecasting
- End-to-End Sales Forecasting KPI Dashboard ETL: https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl
- E-commerce Power BI Dashboard: https://github.com/stalcup-dev/ecommerce-powerbi-dashboard

### Modeling & survey analytics
- Insurance Cost Analysis: https://github.com/stalcup-dev/insurance-cost-analysis
- GSS Happiness — Adjusted Effects: https://github.com/stalcup-dev/gss-happiness-adjusted-effects
- Stack Overflow 2024 Trends: https://github.com/stalcup-dev/stack-overflow-2024-trends

### Tools & automation
- Local AI Privacy Control — Offline Document Assistant: https://github.com/stalcup-dev/local-ai-privacy-control
- Extracting and Visualizing Stock Data: https://github.com/stalcup-dev/Extracting-and-Visualizing-Stock-Data

---

## About me

I’m a **Medical Laboratory Technician (8+ years)** transitioning into **RevOps / RCM analytics and BI**.

What I bring:
- Strong **operations-first mindset** (SLA, TAT, QC, root-cause orientation).
- Experience translating technical outputs into **decision language**.
- Comfort in **async/remote collaboration** and documented workflows.

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-Data_Visualization-F2C811?style=flat&logo=powerbi&logoColor=black)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_Analytics-00AEEF?style=flat)
![Remote](https://img.shields.io/badge/Open_to-Remote_Work-6cc24a?style=flat)

---

## Certifications

- **IBM Data Analyst Professional Certificate** (completed in ~3.5 months): [Certificate image](certificates/ibm-data-analyst-professional-certificate.png) · [Coursera verification](https://www.coursera.org/account/accomplishments/specialization/certificate/VFYV9RUV1HWW)
- **Python for Everybody (Coursera)** — completed

---

## Contact

Open to **remote RevOps Analyst, Revenue Cycle Analyst, and RCM Analyst** opportunities.

- GitHub: https://github.com/stalcup-dev
- Email: allen.stalc@gmail.com
