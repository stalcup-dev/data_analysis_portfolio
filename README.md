# Allen Stalcup — Healthcare Data Analyst Portfolio

## Quick navigation
- [Healthcare-focused 60-second scan](#healthcare-focused-60-second-scan)
- [Healthcare-first project path](#healthcare-first-project-path)
- [Decision-ready business outcomes](#decision-ready-business-outcomes)
- [Role fit: healthcare analyst (revenue cycle + operations)](#role-fit-healthcare-analyst-revenue-cycle--operations)
- [Case studies](#case-studies-best-starting-point)
- [Core skills (with evidence)](#core-skills-with-evidence)
- [Featured project snapshots](#featured-project-snapshots)
- [Full project catalog](#full-project-catalog)
- [About me](#about-me)
- [Certifications](#certifications)
- [Dashboard gallery](#dashboard-gallery)
- [Contact](#contact)

## Healthcare-focused 60-second scan

I’m targeting **remote Healthcare Analyst, Revenue Cycle Analyst, RevOps Analyst, and RCM Analyst** roles (plus Data Analyst / BI roles with revenue ownership).

I build **decision-ready analytics** with reproducible workflows: clear business question → validated analysis → stakeholder-facing recommendation.

### Start here (fastest way to evaluate fit)
- **Healthcare revenue cycle + claims operations:** [Revenue Cycle Healthcare Claims](case_studies/revenue_cycle_healthcare_claims.md) → [Healthcare Claims Analysis](case_studies/healthcare_claims_analysis.md)
- **Commercial margin, pricing, and cost-to-serve analytics:** [MarginMap](https://github.com/stalcup-dev/marginmap) (policy simulator + decision framing) · [Case study](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md)
- **Forecasting + KPI automation:** [Sales Forecasting & KPI Dashboard](case_studies/sales_forecasting_kpi_dashboard.md)
- **Healthcare operations (secondary ops proof):** [Lab SLA & QC Analytics (SQL)](case_studies/lab_sla_qc_analytics.md)
- **Healthcare policy trend context:** [Medicaid Spending Open Analysis](https://github.com/stalcup-dev/medicaid-spending-open-analysis)
- **Cross-functional decision quality (secondary):** [A/B Marketing Experiment — Ad vs PSA](case_studies/ab_marketing_experiment.md)

### Quick review path
1. Open **Start here** links in order: healthcare revenue cycle → margin/cost-to-serve → forecasting/KPI automation.
2. Skim **Decision-ready business outcomes** for quantified impact signals.
3. Open **Featured project snapshots** for concise business question → approach → result summaries.

### What this portfolio demonstrates
- I scope ambiguous business questions into measurable KPIs and explicit decision criteria.
- I pair analysis with QA guardrails (validation checks, assumptions, and caveats) before recommendations.
- I deliver stakeholder-facing outputs (decision packs, case studies, and KPI-ready summaries), not just notebooks.

## Healthcare-first project path

### Tier 1: Core healthcare analytics proof
- **Revenue cycle claims analytics:** denial and AR performance signals mapped to workflow fixes. ([Repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims) | [Case study](case_studies/revenue_cycle_healthcare_claims.md))
- **RCM improvement plan:** structured roadmap to prioritize denial reduction, AR cleanup, and workflow-level fixes. ([Repo](https://github.com/stalcup-dev/rcm-improvement-plan))
- **Healthcare claims KPI concentration analysis:** cost concentration and KPI memoing for prioritization. ([Repo](https://github.com/stalcup-dev/healthcare-claims-analysis) | [Case study](case_studies/healthcare_claims_analysis.md))
- **Healthcare encounters analysis:** encounter-level trend and utilization diagnostics translated into decision-ready priorities. ([Repo](https://github.com/stalcup-dev/encounters-submission-qa-evidence-pack))
- **Healthcare operations SQL analytics:** SLA/TAT bottlenecks and operational recommendations. ([Repo](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis) | [Case study](case_studies/lab_sla_qc_analytics.md) | [Key results](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis#tldr-key-results))
- **Medicaid spending open analysis:** national Medicaid spending trends and cost drivers translated into clear follow-up priorities. ([Repo](https://github.com/stalcup-dev/medicaid-spending-open-analysis) | [Story pack](https://github.com/stalcup-dev/medicaid-spending-open-analysis))

### Tier 2: Margin, forecasting, and adjacent decision science
- **MarginMap (pricing, margin & supply chain analytics):** cost-to-serve visibility, margin leakage diagnostics, and what-if policy simulation for commercial teams. ([Repo](https://github.com/stalcup-dev/marginmap) | [Case study](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md))
- **Forecasting + BI delivery:** ETL → forecasting → KPI dashboard pipeline for planning and reporting workflows. ([Repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl) | [Dashboard image](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png))
- **Cohort retention decision pack:** activation/retention cohort diagnostics tied to RevOps prioritization. ([Repo](https://github.com/stalcup-dev/cohort-retention-decision-pack) | [Case study](case_studies/cohort_retention_decision_pack.md))
- **Steam decision pack:** market, pricing, and launch-timing signals turned into a ship-ready recommendation memo. ([Repo](https://github.com/stalcup-dev/steam-growth-decision-pack-public) | [Case study](case_studies/steam_decision_pack.md))
- **A/B experiment (ship/no-ship decision):** SRM checks, lift analysis, and decision memo (kept as method-quality proof, not a lead portfolio signal). ([Repo](https://github.com/stalcup-dev/marketing-ab-experiment) | [Decision pack](https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports))

## Decision-ready business outcomes
- In revenue-cycle claims analytics, quantified **$22.9K in denied proxy exposure** and concentrated **91.1% of prevented-exposure proxy** in the top 2 denial buckets, converting a diffuse denial pattern into a focused prevention priority set.
- In revenue-cycle claims analytics, isolated **AUTH_ELIG / Noncovered** as the top driver at **$13.7K across 230 claims** and routed **100% of top-25 queue items** to the Eligibility/Auth team for evidence-first handling.
- In revenue-cycle claims analytics, built root-cause intelligence that concentrated **98.3% of weighted priority** in the top 2 buckets and traced **93.7% of AUTH_ELIG dollars** to a single coverage-verification / ABN workflow pattern.
- In encounter-submission QA, triaged **219 defects** across a 10-week validation window and closed **100% of critical submission risk** before release (**80 BLOCKER, 18 HIGH resolved pre-submission; 0 unresolved critical defects at close**).
- In encounter-submission QA, concentrated remediation on the highest-friction defect drivers: the top 5 reject codes accounted for **~59% of all rejects (130/219)**, creating a targeted defect-prioritization path for vendor and operations follow-up.
- In encounter-submission QA, managed **3 batch-level anomaly events** using explicit release gates (duplicate rate >1%, eligibility mismatch >2%, volume shift >15%) and finished the story window with **no unresolved anomaly flags at close**.
- Built a forecasting + KPI automation pipeline with **median MAPE ~12.3%**, **~80% interval coverage**, and near-zero holdout bias, then published outputs for repeatable planning/reporting use.
- In MarginMap, built a cost-to-serve + margin diagnostic workflow and translated product mix, logistics, and pricing signals into decision-ready policy levers (explicitly framed as directional in the case study).

## Role fit: healthcare analyst (revenue cycle + operations)
- KPI design for healthcare revenue workflows: denial rate, AR aging, concentration, throughput, and SLA/TAT.
- Root-cause segmentation by payer/provider/process step to support prioritization.
- Decision memos and stakeholder summaries that connect analytics to operational actions.

## Quantified impact playbook (how I address the “directional vs delta” gap)
For projects where production post-implementation outcomes are not yet available, I now include a standard quantification block:
1. **Baseline**: current metric level + period (e.g., denial rate over trailing 8 weeks).
2. **Effect estimate**: expected point estimate + confidence band from analysis or benchmark.
3. **Business translation**: convert effect into dollars/hours/cycle-time with explicit assumptions.
4. **Decision threshold**: define what effect size justifies ship/scale/no-ship.
5. **30/60/90 follow-up**: pre-committed check-in metrics to validate realized impact vs estimate.

This format is now documented in case studies so hiring teams can see both analytical findings and implementation-grade impact math.

---

## Case studies (best starting point)

### Healthcare-first order
- [Revenue Cycle Healthcare Claims — Denials & AR Focus](case_studies/revenue_cycle_healthcare_claims.md)
- [Healthcare Claims Analysis](case_studies/healthcare_claims_analysis.md)
- [Lab SLA & QC Analytics (SQL)](case_studies/lab_sla_qc_analytics.md)

### Additional analytics projects
- [Cohort Retention Decision Pack](case_studies/cohort_retention_decision_pack.md)
- [MarginMap Supply Chain Analytics — Policy Simulator Case Study](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md)
- [A/B Marketing Experiment — Ad vs PSA](case_studies/ab_marketing_experiment.md)
- [Steam Decision Pack](case_studies/steam_decision_pack.md)
- [Sales Forecasting & KPI Dashboard (Vita Markets)](case_studies/sales_forecasting_kpi_dashboard.md)
- [GSS Happiness — Adjusted Effects (Survey Inference)](case_studies/gss_happiness_adjusted_effects.md)
- [Stack Overflow 2024 Developer Survey — Tech Trends](case_studies/stack_overflow_2024_trends.md)

| Case Study | Domain | Outcome highlight |
| --- | --- | --- |
| Revenue Cycle Healthcare Claims | Healthcare revenue cycle | Denial + AR prioritization workflow |
| Healthcare Claims Analysis | Healthcare analytics | KPI summary + concentration signals |
| Lab SLA & QC Analytics | Healthcare operations | Bottleneck diagnosis and SLA improvement plan |
| Cohort Retention Decision Pack | RevOps / Growth analytics | Activation + retention-driven prioritization |
| MarginMap | Commercial / pricing + supply chain analytics | Margin visibility, supply chain cost signals, and policy what-if support |
| A/B Marketing Experiment — Ad vs PSA | Experimentation | Lift analysis + no-ship decision memo |
| Steam Decision Pack | Gaming market analytics | Pricing and launch recommendation memo |
| Sales Forecasting & KPI Dashboard | E-commerce / Forecasting | Forecast performance + dashboard delivery |
| GSS Happiness — Adjusted Effects | Survey inference | Adjusted effects with inference guardrails |
| Stack Overflow 2024 Trends | Survey analytics | Stakeholder-ready trend synthesis |

---

## Core skills (with evidence)

| Skill | What I can do | Evidence |
|---|---|---|
| Healthcare / RevOps / RCM analytics | Denial trends, AR drivers, KPI monitoring, and prioritization playbooks | [Revenue cycle case study](case_studies/revenue_cycle_healthcare_claims.md) |
| Healthcare operations analytics | SLA/TAT monitoring, bottleneck diagnosis, and process-level action plans | [Lab SLA & QC analytics case study](case_studies/lab_sla_qc_analytics.md) |
| Cohort retention analytics | Cohort construction, activation/retention diagnostics, and action prioritization | [Cohort retention case study](case_studies/cohort_retention_decision_pack.md) |
| Margin, pricing & supply chain analytics | Unit economics, supply chain cost-to-serve segmentation, and what-if policy simulation for pricing decisions | [MarginMap repo](https://github.com/stalcup-dev/marginmap) · [Case study](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md) |
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

**Links:** [Repo](https://github.com/stalcup-dev/medicaid-spending-open-analysis) · [Story pack](https://github.com/stalcup-dev/medicaid-spending-open-analysis)

### 4) Cohort Retention Decision Pack
**Business question:** Which lifecycle stages are driving retention drop-off, and where should RevOps focus first?

**Approach:** Cohort-based activation and retention analysis with segment-level diagnostics and prioritization framing.

**Result:** Identified the highest-impact retention gaps and translated findings into a focused action plan for follow-up experiments.

**Links:** [Repo](https://github.com/stalcup-dev/cohort-retention-decision-pack) · [Case study](case_studies/cohort_retention_decision_pack.md)

### 5) Steam Decision Pack
**Business question:** Which release/pricing strategy should be prioritized for a Steam launch decision?

**Approach:** Product and competitor segmentation, price-band benchmarking, and recommendation framing in a decision-pack format.

**Result:** Produced a concise recommendation memo with assumptions, risks, and next-step validation checks.

**Links:** [Repo](https://github.com/stalcup-dev/steam-growth-decision-pack-public) · [Case study](case_studies/steam_decision_pack.md)

### 6) A/B Marketing Experiment — Ad vs PSA
**Business question:** Should we ship ad creative based on measured lift?

**Approach:** Data QA + SRM checks, hypothesis testing, confidence intervals, practical-significance framing.

**Result:** Detected randomization risk (SRM) and recommended **no-ship** until rerun with clean assignment.

**Links:** [Repo](https://github.com/stalcup-dev/marketing-ab-experiment) · [Decision pack](https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports)

### 7) MarginMap
**Business question:** Which products, customer groups, pricing choices, and supply chain costs are squeezing profit, and what should teams fix first?

**Approach:** Built a margin and supply chain analytics workflow that breaks down revenue, cost, and product mix in plain language, then tests policy changes with a what-if simulator.

**Result:** Produced a clear action roadmap showing where margin is leaking, which levers improve profit fastest, and how policy changes could affect outcomes before rollout.

**Links:** [Repo](https://github.com/stalcup-dev/marginmap) · [Case study](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md)

### 8) Sales Forecasting & KPI Dashboard (ETL + BI)
**Business question:** Can raw sales data become refreshable planning KPIs + reliable forecasts?

**Approach:** PostgreSQL + dbt modeling → Python forecasting pipeline → Power BI reporting.

**Result:** Reported holdout performance (median MAPE ~12.3%, ~80% coverage) and delivered a repeatable KPI workflow.

**Links:** [Repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl) · [KPI dashboard](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png)

### 9) Lab SLA & QC Analytics (SQL)
**Business question:** Where are SLA misses concentrated, and what operational actions reduce delay risk?

**Approach:** Shift/site/analyte segmentation, p95 TAT analysis, QC-proximity impact checks.

**Result:** Isolated day-shift and ED bottlenecks and identified QC-adjacent periods as major risk multipliers.

**Links:** [Repo](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis) · [Case study](case_studies/lab_sla_qc_analytics.md)

---

## Full project catalog

### Healthcare, RevOps & operations
- Revenue Cycle Healthcare Claims: https://github.com/stalcup-dev/revenue-cycle-healthcare-claims
- RCM Improvement Plan: https://github.com/stalcup-dev/rcm-improvement-plan
- Healthcare Encounters Analysis: https://github.com/stalcup-dev/encounters-submission-qa-evidence-pack
- Healthcare Claims Analysis: https://github.com/stalcup-dev/healthcare-claims-analysis
- Medicaid Spending Open Analysis: https://github.com/stalcup-dev/medicaid-spending-open-analysis
- Cohort Retention Decision Pack: https://github.com/stalcup-dev/cohort-retention-decision-pack
- SQL Lab Insights & SLA Analysis: https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis
- Chemistry QC Automation & Westgard Rules: https://github.com/stalcup-dev/chemistry-qc-automation

### Experimentation
- A/B Marketing Experiment — Ad vs PSA: https://github.com/stalcup-dev/marketing-ab-experiment

### Market analytics
- Steam Decision Pack: https://github.com/stalcup-dev/steam-growth-decision-pack-public

### E-commerce & forecasting
- MarginMap: https://github.com/stalcup-dev/marginmap · Case study: https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md
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

I’m a **Medical Laboratory Technician (8+ years)** transitioning into **healthcare analytics, RevOps / RCM analytics, and BI**.

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
- **Revenue Cycle, Billing, and Coding** — Johns Hopkins University (Course) · Completed February 2026
- **Python for Everybody (Coursera)** — completed


## Dashboard gallery

### Revenue Cycle (RCM) dashboard
[RCM project repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims)

![Revenue Cycle dashboard preview](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims/blob/main/docs/images/tab1.png?raw=1)

If the preview does not render in your viewer, open it directly in the project repo: [RCM dashboard image](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims/blob/main/docs/images/tab1.png).

### MarginMap policy simulator dashboard
[MarginMap supply chain analytics case study](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md)

![MarginMap policy simulator dashboard](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/assets/screenshots/07_policy_simulator.png?raw=1)

If the preview does not render in your viewer, open it directly: [Policy simulator screenshot](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/assets/screenshots/07_policy_simulator.png).

### Sales & Forecasting dashboards
[Sales forecasting project repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl)

![Sales KPI dashboard](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png)

![Sales forecasting dashboard](https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/ForecastingDash.png)

---

## Contact

Open to **remote Healthcare Analyst, RevOps Analyst, Revenue Cycle Analyst, and RCM Analyst** opportunities.

- GitHub: https://github.com/stalcup-dev
- Email: allen.stalc@gmail.com
