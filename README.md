# Allen Stalcup — Healthcare / Revenue Cycle Data Analyst Portfolio

I build decision-ready analytics for healthcare revenue cycle and regulated operations workflows, with explicit assumptions, QA checks, and stakeholder-facing recommendations.

This portfolio is best aligned to healthcare analytics, revenue cycle, and operations-focused analyst roles.

## Featured Project

### Revenue Integrity Control Room Prototype
[Repo case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md) · [Repo](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype)

- Integrates claims-integrity risk, AR pressure, and denial concentration into one operating view for faster prioritization.
- Emphasizes financial-impact routing so follow-up capacity is directed to the highest-value cohorts first.
- Supports operational control with transparent KPI logic and decision-ready drilldowns for leaders and analysts.
- Strengthens decision support by linking prevention actions (front-end quality) with recovery actions (back-end collections).

## Start here

### Flagship projects (4)
1. **Revenue Integrity Control Room Prototype** — integrated revenue-integrity monitoring for risk prioritization and action routing.
   [Repo case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md) · [Repo](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype)
2. **Revenue Cycle Healthcare Claims** — denial and AR analytics translated into workflow-level prioritization for RCM teams.
   [Case study](case_studies/revenue_cycle_healthcare_claims.md) · [Repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims)
3. **Healthcare Claims Analysis** — concentration and KPI analysis to focus follow-up effort on highest-impact claim drivers.
   [Case study](case_studies/healthcare_claims_analysis.md) · [Repo](https://github.com/stalcup-dev/healthcare-claims-analysis)
4. **Lab SLA & QC Analytics (SQL)** — healthcare operations analysis that isolates turnaround-time bottlenecks and QC-adjacent delay risk.
   [Case study](case_studies/lab_sla_qc_analytics.md) · [Repo](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis)

### Review path
For a fast screen: review the featured control-room case study first, then the remaining flagship case studies in order; skim Supporting Projects for secondary depth.

## Decision-ready proof
### Cross-project portfolio proof (existing)
*Reference note: each bullet links to the source artifact location where the cited metric is documented.*
- **Observed in analysis:** Revenue-cycle work quantified **$22.9K denied proxy exposure**, with **91.1% of prevented-exposure proxy** concentrated in the top two denial buckets, turning a broad denial pattern into a focused work queue ([Evidence repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims)).
- **Observed in analysis:** Revenue-cycle root-cause prioritization concentrated **98.3% of weighted priority** in the top two denial buckets, tightening follow-up around the highest-value workflow issues ([Evidence repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims)).
- **Observed in analysis:** Encounter-submission QA triaged **219 defects** and closed with **0 unresolved critical defects** (80 BLOCKER + 18 HIGH resolved pre-submission) ([Evidence repo](https://github.com/stalcup-dev/encounters-submission-qa-evidence-pack)).
- **Observed in holdout / validation:** Forecasting pipeline reported **median MAPE ~12.3%** with **~80% interval coverage** for repeatable planning outputs ([Case study](case_studies/sales_forecasting_kpi_dashboard.md) · [Evidence repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl)).

### Revenue Integrity Control Room report addendum
- **Observed in shipped control-room output:** the current deterministic outpatient slice surfaced **24 open exceptions** and **$13.37K gross exposure**, with **72.9% still recoverable** (**$9.74K**) and **27.1% already lost** (**$3.63K**); **70.8% of exceptions were SLA-breaching**, turning broad charge-capture leakage into a ranked, owner-routed work queue ([Evidence case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md) · [Featured story image](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/artifacts/reviewer_walkthrough_pack/summary_featured_story.png?raw=1)).
- **Observed in shipped prioritization:** the top three active queues narrowed action to **billing prebill holds, documentation support, and coding review**, each with explicit owner, recoverability, and next-step guidance; the top queue alone represented about **63% of active exposure** (**$8.4K**), with about **29.8% of that queue still recoverable** (**$2.5K**) ([Evidence case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md)).
- **Observed in case-level governance proof:** the featured OR case preserved the same failed-control story across summary, proof, and exported memo, keeping failed control, root cause, blocker, owner, aging, and recoverability aligned end to end ([Evidence case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md)).
- **Observed in browser-visible governance proof:** selected cases surface one current blocker, accountable owner, stage age, SLA status, recoverability, and routing history in the working app (not only in export artifacts) ([Evidence case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md)).
- **Observed in realism / validation:** the shipped realism artifact passed **22/22 checks** with **0 warnings** and **0 failures**, including **0 one-current-blocker violations** and **100% routing-reason coverage** ([Evidence case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md)).

### Use with caution
- **Modeled estimate only:** Scenario Lab outputs are **what-if projections**, not forecasts; default levers project 4 fewer backlog items, +16.6 SLA points, and a $2,464 recoverable-dollar lift.
- **Scope guard:** this portfolio evidence is deterministic, synthetic, facility-side, and outpatient-first proof; it is **not** production deployment evidence, realized ROI, live hospital outcomes, or forecast-accuracy proof.
- **Realism report context:** the shipped realism artifact (**22/22 checks passed**) supports internal consistency and governance traceability for this synthetic prototype; it does not convert this work into live-deployment or realized-outcome evidence.

To protect credibility across projects:
- **Modeled estimate** = directional impact projection from scenario analysis.
- **Operational target** = implementation goal set for a team/process.
- **Validation plan** = post-change 30/60/90 metric check to compare realized vs expected impact.

## Flagship case studies

### 1) Revenue Integrity Control Room Prototype
- **Business question:** Which claims-integrity risks should be prioritized now to reduce preventable leakage and AR drag?
- **What this shows:** Control-room style KPI integration, risk-based routing logic, and executive-friendly operational decision support.
- **Evidence:** [Repo case study](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md) · [Repo](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype)

### 2) Revenue Cycle Healthcare Claims
- **Business question:** Which denial and AR drivers should be prioritized first to reduce preventable revenue leakage?
- **What this shows:** RCM KPI design, concentration logic, root-cause framing, and action routing tied to operational teams.
- **Evidence:** [Case study](case_studies/revenue_cycle_healthcare_claims.md) · [Repo](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims)

### 3) Healthcare Claims Analysis
- **Business question:** Where are healthcare claims costs concentrated, and what should be prioritized first?
- **What this shows:** Healthcare claims segmentation, KPI computation, and memo-ready prioritization for analyst-to-leadership communication.
- **Evidence:** [Case study](case_studies/healthcare_claims_analysis.md) · [Repo](https://github.com/stalcup-dev/healthcare-claims-analysis)

### 4) Lab SLA & QC Analytics (SQL)
- **Business question:** Where are SLA misses concentrated, and which operational fixes should be prioritized first?
- **What this shows:** SQL-based bottleneck analysis, p95 turnaround-time review, and healthcare operations problem framing grounded in lab workflows.
- **Evidence:** [Case study](case_studies/lab_sla_qc_analytics.md) · [Repo](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis)

## Supporting projects (secondary evidence)

### Healthcare operations depth
- [Healthcare Encounters Analysis](https://github.com/stalcup-dev/encounters-submission-qa-evidence-pack)
- [Medicaid Spending Open Analysis](https://github.com/stalcup-dev/medicaid-spending-open-analysis)
- [RCM Improvement Plan](https://github.com/stalcup-dev/rcm-improvement-plan)

### Forecasting / BI depth
- [Sales Forecasting & KPI Dashboard](case_studies/sales_forecasting_kpi_dashboard.md) · [Repo](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl)
- [Cohort Retention Decision Pack](case_studies/cohort_retention_decision_pack.md) · [Repo](https://github.com/stalcup-dev/cohort-retention-decision-pack)
- [MarginMap (directional scenario analysis)](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/docs/CASE_STUDY.md) · [Repo](https://github.com/stalcup-dev/marginmap-supply-chain-analytics)

### Secondary method / experimentation / market work
- [A/B Marketing Experiment — Ad vs PSA](case_studies/ab_marketing_experiment.md) · [Repo](https://github.com/stalcup-dev/marketing-ab-experiment)
- [Steam Decision Pack](case_studies/steam_decision_pack.md) · [Repo](https://github.com/stalcup-dev/steam-growth-decision-pack-public)
- [Stack Overflow 2024 Trends](case_studies/stack_overflow_2024_trends.md)
- [GSS Happiness — Adjusted Effects](case_studies/gss_happiness_adjusted_effects.md)

## Skills / tools (evidence-linked)
- **Healthcare / RCM analytics:** denial trends, AR drivers, KPI concentration, workflow prioritization ([Revenue Cycle case study](case_studies/revenue_cycle_healthcare_claims.md)).
- **Healthcare operations analytics:** SLA/TAT bottleneck analysis and operational follow-up framing ([Lab SLA & QC](case_studies/lab_sla_qc_analytics.md)).
- **SQL + Python analytics:** reproducible pipelines, segmentation logic, and QA checks ([SQL Lab project](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis)).
- **Forecasting + BI delivery:** ETL/model/reporting workflow with holdout validation ([Forecasting project](case_studies/sales_forecasting_kpi_dashboard.md)).
- **Decision science communication:** concise memos with assumptions, risks, and next-step tests ([A/B case study](case_studies/ab_marketing_experiment.md)).

**Tech stack:** Python, SQL (PostgreSQL), pandas, dbt, Power BI, Tableau, Git/GitHub.

## About
Medical Laboratory Technician (8+ years) with frontline experience in regulated healthcare operations (SLA/TAT pressure, QC discipline, and escalation workflows), now applying that context to healthcare analytics, revenue-cycle analytics, and operations-focused BI.

## Certifications
- **IBM Data Analyst Professional Certificate** — [Certificate image](certificates/ibm-data-analyst-professional-certificate.png) · [Coursera verification](https://www.coursera.org/account/accomplishments/specialization/certificate/VFYV9RUV1HWW)
- **Revenue Cycle, Billing, and Coding** — Johns Hopkins University (Course), completed Feb 2026
- **Python for Everybody (Coursera)**

## Visual proof (compact)
**Revenue Integrity Control Room — featured story**  
![Revenue Integrity Control Room featured story](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/artifacts/reviewer_walkthrough_pack/summary_featured_story.png?raw=1)

**Revenue Cycle dashboard preview**  
![Revenue Cycle dashboard preview](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims/blob/main/docs/images/tab1.png?raw=1)

**MarginMap policy simulator (scenario view)**  
![MarginMap policy simulator](https://github.com/stalcup-dev/marginmap-supply-chain-analytics/blob/main/assets/screenshots/07_policy_simulator.png?raw=1)

MarginMap is included here intentionally: it is less healthcare-specific, but it demonstrates transferable depth in scenario modeling, cost-to-serve analysis, policy simulation, and product-style analytics.

For additional screenshots and dashboard context, open the linked project repositories and case studies above.

## Contact
Open to remote Healthcare Analyst, Revenue Cycle Analyst, RCM Analyst, and Operations Analyst roles.

- GitHub: https://github.com/stalcup-dev
- Email: allen.stalc@gmail.com
