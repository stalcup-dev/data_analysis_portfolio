# Revenue Cycle Healthcare Claims — Denials, AR, and Workqueue Prioritization

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_Analytics-00AEEF?style=flat)

## TL;DR
- Built an RCM-focused analysis to identify where denials and AR delays create the most downstream rework.
- Prioritized payer/provider/denial-reason segments into an action queue for prevention and faster resolution.
- Framed outputs for RevOps/RCM stakeholders using KPI definitions, segmentation logic, and decision-ready recommendations.

## Business Question
Where is revenue leakage most concentrated in the claims workflow, and which fixes should be prioritized first to improve clean-claim performance and AR velocity?

## Stakeholder + Use Case
- **Primary audience:** Revenue Cycle Manager, Billing Operations Lead, RevOps analyst partners.
- **Decision supported:** Which denial/AR segments should be tackled first this sprint/month.
- **Operating cadence:** KPI review and workqueue reprioritization.

## Data Scope
- Portfolio-safe claims workflow data from the linked repository.
- Typical fields used in analysis include payer, provider, claim status, denial reason, AR days, and rework indicators.
- Scope is intentionally project-bounded (demonstration analysis, not enterprise production volume).

## KPI Framework
| KPI | Why it matters |
| --- | --- |
| Denial rate | Early signal of preventable leakage and rework burden |
| Clean-claim rate | Front-end process quality indicator |
| AR days / aging buckets | Cash-velocity and follow-up effectiveness signal |
| Rework volume | Capacity drain and avoidable cost proxy |

## Analytical Approach
1. **Define KPI logic** for denials, clean claims, AR aging, and rework.
2. **Segment denials** by payer, provider, and denial reason to find concentration.
3. **Profile AR aging** to isolate high-latency cohorts and follow-up pressure points.
4. **Map findings to actions** (front-end prevention vs back-end follow-up playbooks).

## Key Findings
- Denials and rework are concentrated in a limited set of payer/reason cohorts, supporting a focused intervention strategy rather than broad process changes.
- AR delay risk is uneven across segments, indicating that payer-specific follow-up cadence is more effective than one-size-fits-all queues.
- Clean-claim opportunities are strongest at intake/coding controls, where upstream fixes can reduce downstream rework volume.

## Recommended Actions
### 1) Front-end denial prevention
- Add targeted eligibility and coding guardrails for top denial cohorts.
- Standardize submission QA checks for high-frequency error pathways.

### 2) AR follow-up optimization
- Use aging + payer segmentation to triage queues by expected recovery impact.
- Assign payer-specific touch patterns to reduce avoidable AR carryover.

### 3) KPI operating rhythm
- Track denial rate, clean-claim rate, AR aging, and rework volume together.
- Run weekly cohort reviews to confirm whether interventions shift the right segments.

## Business Impact (Portfolio Context)
- Demonstrates ability to turn claims data into a ranked action plan tied to operational execution.
- Shows RevOps/RCM readiness: metric design, root-cause segmentation, and stakeholder-facing decision support.

## Artifacts
- Repo: https://github.com/stalcup-dev/revenue-cycle-healthcare-claims
- Project README and analysis outputs: https://github.com/stalcup-dev/revenue-cycle-healthcare-claims#readme
- Portfolio README reference: [Main portfolio README](../README.md)

## Tech + Skills Demonstrated
- Python and SQL for KPI computation and segmentation analysis
- Revenue cycle analytics: denials, AR, rework, clean-claim performance
- Decision communication for operations and finance-adjacent stakeholders
