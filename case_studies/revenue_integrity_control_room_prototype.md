# Revenue Integrity Control Room Prototype

![Healthcare Revenue Cycle](https://img.shields.io/badge/Domain-Healthcare_Revenue_Cycle-00AEEF?style=flat)
![Decision Support](https://img.shields.io/badge/Focus-Operational_Decision_Support-4B8BBE?style=flat)
![Prototype](https://img.shields.io/badge/Stage-Prototype-6A737D?style=flat)

## Project Title
**Revenue Integrity Control Room Prototype** — a healthcare revenue-cycle analytics concept for monitoring claim-quality risk, workqueue pressure, and financial exposure in one operating view.

> **Evidence note:** This portfolio summarizes deterministic, synthetic, outpatient-first control-room outputs intended for decision support and governance traceability, not production ROI claims or forecasts.
> **Realism report context:** The shipped realism artifact (**22/22 checks passed**) supports internal consistency and governance traceability for this synthetic prototype; it does not constitute live-hospital outcome or deployment proof.

## Business Context
Healthcare revenue cycle teams often work across disconnected reports (denials, edits, aging, productivity), which slows prioritization and creates avoidable leakage. A “control room” approach centralizes risk and performance indicators so operations leaders can direct limited follow-up capacity toward the highest-value claims first.

## Problem Statement
Revenue integrity issues are usually visible only after claims age or deny, by which point remediation is slower and costlier. Teams need a single view that flags where process breakdowns are emerging (registration, coding, charge capture, payer rules) before they compound into AR drag and write-off risk.

## Objectives & Success Metrics
- Build a decision-ready control-room view for daily/weekly RCM operating cadence.
- Rank claim cohorts by financial risk and operational urgency.
- Support faster intervention routing across front-end and back-end teams.

**Success metrics (prototype targets):**
- Reduction in preventable denial rate for prioritized cohorts.
- Lower share of AR in high-latency buckets (for example, >60 days).
- Higher first-pass / clean-claim performance.
- Decrease in manual rework touches per claim.

## Data & Methodology
- Revenue-cycle workflow data expected to include payer, claim status, denial reason, aging, and claim value fields.
- Metric layer combines outcome KPIs (denials, AR aging, rework) with leading indicators (edit fail patterns, queue load, trend acceleration).
- Segmentation-first methodology to isolate concentration by payer, service line, location, and reason category.

## Analytics / Modeling Approach
- Cohort concentration analysis to identify “vital few” drivers of leakage.
- Risk scoring logic (expected financial exposure × probability of delay/denial) to prioritize queues.
- Threshold-based alerting for abnormal shifts in denial mix or aging trajectory.
- Scenario framing to compare impact of prevention actions vs recovery actions.

## Dashboard or Product Experience
The prototype control room is positioned as an executive-to-operator bridge:
- **Executive layer:** current exposure, trend direction, top risk cohorts, intervention status.
- **Manager layer:** payer/reason drilldowns, queue balance, SLA pressure, ownership routing.
- **Analyst layer:** cohort definitions, metric logic transparency, QA checks, and traceable assumptions.

## Key Insights & Recommendations
- Focus first on high-concentration denial cohorts rather than broad process overhauls.
- Pair financial risk ranking with operational capacity so teams can execute, not just diagnose.
- Separate prevention plays (registration/coding/edits) from recovery plays (AR follow-up cadence) to improve accountability.
- Institutionalize weekly variance review to confirm interventions are changing the intended cohorts.

## Business Impact (Actual or Expected)
**Expected impact profile (to validate post-implementation):**
- Improved claims integrity through earlier detection of defect patterns.
- Faster management response to adverse trend shifts in denials and AR.
- Higher value per follow-up hour by routing teams to risk-adjusted priorities.
- Better leadership visibility into whether interventions produce measurable financial lift.

## Tech Stack
- Python (data wrangling, KPI logic, risk scoring)
- SQL (cohort extraction, aggregations, metric views)
- BI/dashboard tooling for control-room experience
- Git/GitHub for versioned analytics and documentation

## How to Reproduce / Explore
1. Clone the project repository.
2. Review project documentation and data dictionary.
3. Run the data prep and metric generation workflow.
4. Open dashboard artifacts and validate metric definitions against source logic.
5. Apply the included prioritization framework to identify top intervention cohorts.

## Latest React App Screenshots (Updated May 25, 2026)

These images reflect the newest React product surface documented in the source project case study.

### 1) React Control Room Summary
![React Control Room Summary (May 25, 2026)](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/raw/main/artifacts/browser_audit/react_control_room_summary_2026-05-25.png)

### 2) React Reviewer Proof Pack Lens
![React Reviewer Proof Pack Lens (May 25, 2026)](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/raw/main/artifacts/browser_audit/react_reviewer_proof_pack_lens_2026-05-25.png)

### 3) React Scenario Claim-Tightening Lens
![React Scenario Claim-Tightening Lens (May 25, 2026)](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/raw/main/artifacts/browser_audit/react_scenario_claim_tightening_lens_2026-05-25.png)

### 4) React Decision Pack Freshness Lens
![React Decision Pack Freshness Lens (May 25, 2026)](https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/raw/main/artifacts/browser_audit/react_decision_pack_freshness_lens_2026-05-25.png)

## Repository Link
- Case study: https://github.com/stalcup-dev/revenue-integrity-control-room-prototype/blob/main/case_study.md
