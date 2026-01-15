# Revenue Cycle Healthcare Claims — Denials & AR Focus

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_Analytics-00AEEF?style=flat)

## TL;DR
- Built a revenue cycle analytics case study that surfaces denial drivers, AR aging risk, and rework hotspots.
- Translated claims workflow signals into operational recommendations (eligibility, coding, follow-up cadence).
- Structured the work so key KPIs and charts are traceable to the analysis artifacts in the repo.

## Business Question
Where are denials and AR delays leaking revenue, and which workflow fixes create the biggest lift?

## Data
- Claims workflow dataset from the repo (e.g., claim status, payer, provider, denial reason, AR days, rework flags).
- Notes: Portfolio-safe dataset; findings reflect the repo’s sample scope.
- **Primary stakeholder:** Revenue cycle director / billing operations lead.
- **Time to deliver:** TBD (self-paced; replace with actual delivery time).

## Approach
- Define revenue cycle KPIs (denial rate, clean-claim rate, AR days, rework volume).
- Segment denials by payer, denial reason, and provider to isolate root causes.
- Analyze AR aging buckets and rework signals to quantify workflow bottlenecks.
- Package outputs into recruiter-ready artifacts (README, charts, analysis notes).

## KPI Definitions (at-a-glance)
| KPI | Definition |
| --- | --- |
| Denial rate | Denied claims ÷ total submitted claims |
| Clean-claim rate | Claims that pass first submission ÷ total submitted claims |
| AR days | Days from claim submission to payment/post date |
| Rework volume | Count of claims requiring resubmission or additional action |

## Key Results (What to highlight)
- **Denial concentration:** Identify the top denial reasons and payers driving most rework.
- **AR aging risk:** Pinpoint aging buckets or provider groups with elevated days in AR.
- **Clean-claim opportunities:** Show where front-end fixes (eligibility/coding) reduce downstream rework.
- **KPI callouts to surface from the repo outputs:** denial rate, clean-claim rate, median AR days, rework volume.
- **Example KPI slots (replace with actuals):** Denial rate: __%; Clean-claim rate: __%; Median AR days: __; Rework volume: __ claims.

## So What (Decision / Impact)
- Prioritize denial prevention at intake (eligibility checks, coding validation) for the highest-volume denial reasons.
- Tighten follow-up cadence and payer-specific playbooks for AR aging hotspots.
- Track clean-claim rate and rework volume as leading indicators of revenue cycle health.

## What This Proves
- Ability to translate healthcare claims workflows into measurable, decision-ready KPIs.
- Skill in finding denial root causes and tying them to operational fixes.

## Artifacts
- Repo: https://github.com/stalcup-dev/revenue-cycle-healthcare-claims
- Primary artifact: [Repo README KPI summary + linked analysis outputs](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims#readme)
- Visual snapshot: Link a chart/dashboard image from the repo (denials by reason, AR aging, or payer mix)
- How to verify:
  - Open the README for KPI definitions and analysis summary.
  - Review linked notebooks/outputs for charts and segmentation tables.

## Tech + Skills Demonstrated
- Revenue cycle KPI design (denials, AR aging, clean-claim rate)
- Segmentation analysis by payer/provider/denial reason
- Decision-ready storytelling for healthcare operations

## Next Steps
- Add payer-specific playbooks using denial reason × payer heatmaps.
- Quantify the impact of clean-claim improvements on AR aging over time.
