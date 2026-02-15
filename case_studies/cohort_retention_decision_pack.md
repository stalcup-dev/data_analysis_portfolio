# Cohort Retention Decision Pack — Activation, Week-1 Retention, and Payback Framing

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![RevOps](https://img.shields.io/badge/Domain-RevOps-5B8DEF?style=flat)

## TL;DR
- Built a cohort-retention decision pack that connects activation and retention behavior to practical go-to-market and lifecycle actions.
- Used cohort and funnel-style segmentation to identify where early drop-off is concentrated.
- Framed outputs as decision support for RevOps and growth stakeholders (what to fix first, and why).

## Business Question
Which acquisition cohorts and onboarding stages are contributing most to early churn, and what actions should be prioritized to improve retention quality and revenue efficiency?

## Stakeholder + Use Case
- **Primary audience:** RevOps, Growth, Lifecycle Marketing, and Product partners.
- **Decision supported:** Prioritize interventions across onboarding, messaging, and channel mix.
- **Operating cadence:** Weekly cohort review + monthly planning.

## KPI Framework
| KPI | Why it matters |
| --- | --- |
| Activation rate | Indicates onboarding quality and first-value realization |
| Week-1 / Week-4 retention | Early signal of product-channel fit and stickiness |
| Cohort decay slope | Highlights where engagement loss accelerates |
| Payback framing proxy | Connects retention quality to efficient spend decisions |

## Analytical Approach
1. Build cohorts by acquisition period/channel and track retention over time.
2. Segment activation and retention by source, onboarding path, and user profile.
3. Compare cohort quality using early-retention indicators and decay patterns.
4. Convert findings into a prioritized decision pack with near-term actions.

## Key Findings
- Early retention variance across cohorts suggests quality differences that are not visible in topline signup volume alone.
- A subset of cohorts appears activation-constrained (drop-off before stable usage), indicating onboarding and messaging fixes should come before scale.
- Channel-level differences support reallocating effort toward cohorts with stronger early retention quality.

## Recommended Actions
### 1) Onboarding optimization
- Reduce time-to-first-value for lower-retention cohorts.
- Tighten activation checkpoints and monitor completion by cohort.

### 2) Channel and lifecycle prioritization
- Rebalance campaign focus toward cohorts with better Week-1/Week-4 performance.
- Add lifecycle nudges for high-risk cohorts during first-week behavior windows.

### 3) RevOps operating rhythm
- Track activation and retention together in weekly cohort reviews.
- Pair trend monitoring with explicit intervention logging to measure lift.

## Business Impact (Portfolio Context)
- Demonstrates ability to turn retention analytics into prioritized, cross-functional action plans.
- Shows RevOps readiness: KPI design, cohort segmentation, and decision-pack communication.

## Artifacts
- Repo: https://github.com/stalcup-dev/cohort-retention-decision-pack
- Project README and outputs: https://github.com/stalcup-dev/cohort-retention-decision-pack#readme
- Portfolio README reference: [Main portfolio README](../README.md)

## Tech + Skills Demonstrated
- Python + SQL for cohort construction, retention analysis, and segmentation
- RevOps/growth analytics: activation, retention, cohort quality, prioritization
- Decision communication for cross-functional stakeholders
