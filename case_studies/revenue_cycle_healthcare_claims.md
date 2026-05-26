# 🏥 Revenue Cycle Healthcare Claims
### Denials Reduction, AR Acceleration & Workqueue Prioritization

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=flat&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat&logo=python&logoColor=white)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_RCM-00AEEF?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

</div>

---

## 📌 TL;DR — What This Project Does and Why It Matters

> **Revenue cycle teams lose thousands of dollars per week to preventable denials and slow AR follow-up. This analysis identifies exactly where that leakage occurs and builds a prioritized action queue to fix it.**

| | |
|---|---|
| 🎯 **Goal** | Pinpoint denial and AR delay concentration so operations teams can act on the right segments first |
| 🏢 **Stakeholders** | Revenue Cycle Manager · Billing Operations Lead · RevOps Analyst Partners |
| 📊 **Output** | Ranked intervention queue + KPI dashboard + 30/60/90 impact validation plan |
| 🛠️ **Stack** | Python (pandas, matplotlib) · SQL (PostgreSQL) |

---

## 🔍 Business Problem

Healthcare organizations routinely lose **5–10% of billed revenue** to claim denials — and a significant portion of that is preventable. Without a clear picture of *where* denials concentrate and *why* AR ages out, RCM teams default to one-size-fits-all playbooks that burn capacity without moving the needle.

**The core question driving this analysis:**

> *Where is revenue leakage most concentrated in the claims workflow, and which fixes should be prioritized first to improve clean-claim performance and AR velocity?*

---

## 📐 KPI Framework

These four metrics form the analytical backbone of the project — each chosen because it signals a distinct failure mode in the revenue cycle:

```
┌──────────────────────┬────────────────────────────────────────────────────────────┐
│ KPI                  │ Why It Matters                                             │
├──────────────────────┼────────────────────────────────────────────────────────────┤
│ Denial Rate          │ Early signal of preventable leakage and rework burden      │
│ Clean-Claim Rate     │ Front-end process quality — measures how much gets right   │
│                      │ on first submission                                        │
│ AR Days / Aging      │ Cash velocity signal — how fast outstanding balances       │
│ Buckets              │ convert to collected revenue                               │
│ Rework Volume        │ Capacity drain proxy — how many touches does each claim    │
│                      │ require before resolution                                  │
└──────────────────────┴────────────────────────────────────────────────────────────┘
```

---

## 🗂️ Data Scope

- **Source:** Portfolio-safe synthetic claims workflow dataset (linked repo below)
- **Key fields:** `payer`, `provider`, `claim_status`, `denial_reason`, `ar_days`, `rework_touches`, `submission_date`, `resolution_date`
- **Scope:** Demonstration-scale dataset; methodology mirrors production RCM analytics patterns

---

## 🔬 Analytical Approach

The analysis follows a four-stage workflow — from metric definition through actionable segmentation:

```
  STAGE 1              STAGE 2              STAGE 3              STAGE 4
┌──────────┐        ┌──────────┐        ┌──────────┐        ┌──────────┐
│  Define  │───────▶│ Segment  │───────▶│ Profile  │───────▶│   Map    │
│ KPI Logic│        │ Denials  │        │ AR Aging │        │ Findings │
│          │        │ by Payer/│        │ by Cohort│        │ to Action│
│ Denial % │        │ Provider/│        │          │        │ Playbooks│
│ AR Days  │        │ Reason   │        │ High-lag │        │          │
│ Rework   │        │          │        │ segments │        │ Prevent  │
│ Clean Clm│        │ Find top │        │ Follow-up│        │   vs.    │
│          │        │ 20% that │        │ pressure │        │ Recover  │
└──────────┘        │ = 80%    │        │ points   │        └──────────┘
                    │ of loss  │        └──────────┘
                    └──────────┘
```

### Step-by-step logic

**1. Define KPI logic**
Compute denial rate, clean-claim rate, AR aging distribution, and rework touches per claim using standardized SQL logic applied consistently across payer/provider segments.

**2. Segment denials (Pareto analysis)**
Rank payer × denial-reason combinations by total denied claim volume. In most RCM datasets, 3–5 cohorts account for 60–80% of all denial volume — confirming where focused intervention pays off most.

**3. Profile AR aging**
Bucket outstanding claims into `0–30`, `31–60`, `61–90`, and `90+` day cohorts. Identify which payers systematically push volume into high-age buckets and model the collection probability decay by bucket.

**4. Map findings to actions**
Categorize each top segment as a **front-end prevention** opportunity (fix before submission) or a **back-end recovery** opportunity (optimize follow-up cadence), then rank by expected impact.

---

## 📊 Visual Walkthrough

### Denial Concentration — Pareto View

The chart below illustrates how denial volume concentrates across payer/reason combinations. The top cohorts (≈20% of segments) account for the majority of all denial activity — validating a focused intervention strategy.

```
Denial Volume by Payer × Reason Cohort (Illustrative)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Payer A — No Auth        ████████████████████  42%  ◀ Priority 1
Payer B — Coding Error   ████████████          24%  ◀ Priority 2
Payer A — Eligibility    ██████                13%  ◀ Priority 3
Payer C — Timely Filing  ████                   9%
Payer B — Duplicate      ██                     5%
All Others               ███                    7%
                         ─────────────────────────
                         Cumulative top 3: 79%
```

> **Analyst takeaway:** Tackling Payer A authorization failures and Payer B coding errors alone addresses nearly two-thirds of denial rework.

---

### AR Aging Distribution — Cohort View

```
AR Aging Bucket Distribution (Illustrative)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
         0–30 days   ██████████████████████  55%   ✅ Low risk
        31–60 days   ████████████            30%   ⚠️  Follow-up needed
        61–90 days   █████                   10%   🔴 High-lag cohort
           90+ days  ██                       5%   🔴 Recovery risk
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
         Target:     Shift 10–20% from >60 buckets → <30 days
```

> **Analyst takeaway:** The 61–90 and 90+ cohorts represent disproportionate collection risk. Payer-specific follow-up cadencing can migrate a significant portion back into recoverable windows.

---

### Rework Touch Frequency — High vs. Low Friction Cohorts

```
Avg Rework Touches per Claim
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
High-friction cohorts   ████████████████  3.8 touches/claim
Mid-friction cohorts    ████████          2.1 touches/claim
Low-friction cohorts    ████              1.2 touches/claim  ← target baseline
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Reduction target: -0.2 to -0.5 touches/claim in top cohorts
→ At 10,000 claims/mo × 15 min/touch × $35/hr loaded cost:
  0.5 touch reduction = ~$43,750 capacity released/month
```

---

## 💡 Key Findings

### Finding 1 — Denial volume is highly concentrated
> Across the claims dataset, the top 3 payer/reason combinations account for ~79% of all denial activity. This is a textbook Pareto pattern — and it means broad process changes are wasteful compared to targeted cohort interventions.

### Finding 2 — AR delay risk is payer-specific, not universal
> High AR aging concentrates in specific payer relationships, not evenly across the book. Payer A and Payer C show systematically longer resolution timelines — indicating the follow-up cadence and escalation path need to be payer-differentiated, not standardized.

### Finding 3 — Upstream fixes outperform downstream recovery
> Clean-claim improvement opportunities are strongest at the intake and coding stage. Each percentage point of clean-claim rate improvement compounds by reducing the downstream rework burden — making front-end guardrails a higher-ROI investment than additional back-end follow-up staffing.

---

## ✅ Recommended Actions

### 🛡️ 1 — Front-End Denial Prevention
*Address root causes before claims leave the building*

| Action | Target cohort | Expected lift |
|--------|--------------|---------------|
| Add eligibility verification at scheduling for Payer A | Payer A — Authorization denials | −40–60% denial rate in cohort |
| Implement real-time coding validation flags for E&M codes | Payer B — Coding errors | −30–50% in cohort |
| Enforce timely filing calendar alerts at submission | Payer C — Timely filing | Near-elimination |

### 📬 2 — AR Follow-Up Optimization
*Make the back-end work smarter, not harder*

- Apply aging-based queue triage: work `61–90` day accounts before `31–60` each cycle
- Build payer-specific touch templates and escalation paths for top AR-aging payers
- Set automated follow-up triggers at Day 35 for payers known to push into `60+` buckets

### 📈 3 — KPI Operating Rhythm
*Lock in a measurement cadence to confirm interventions are working*

- Weekly cohort review: denial rate + clean-claim rate delta vs. prior period
- Bi-weekly AR aging distribution snapshot: track bucket migration over time
- Monthly rework touch audit: confirm capacity savings are materializing

---

## 📉 Quantified Impact Plan

| Metric | Baseline | Target Delta | Business Value Translation |
|--------|----------|-------------|---------------------------|
| **Denial rate** | Trailing 8-week % by payer/reason | −1 to −3 pp in priority cohorts | `claims volume × denial-rate reduction × avg net reimbursement` = avoided leakage |
| **AR >60 days share** | Trailing 8-week aging distribution | −10% to −20% in targeted queues | `accounts shifted × collection probability gain` = accelerated cash |
| **Rework touches/claim** | Baseline in high-friction cohorts | −0.2 to −0.5 touches/claim | `touches avoided × avg handle time × loaded labor rate` = capacity released |

### 📅 30 / 60 / 90 Day Validation Plan

```
  Day 1–30                  Day 31–60                 Day 61–90
┌─────────────────┐       ┌─────────────────┐       ┌─────────────────┐
│   ADOPTION      │──────▶│   MEASUREMENT   │──────▶│   REPORTING     │
│                 │       │                 │       │                 │
│ • Eligibility   │       │ • Compare denial│       │ • Convert deltas│
│   guardrails    │       │   & AR deltas   │       │   to annualized │
│   live          │       │   vs. pre-period│       │   dollar impact │
│ • Queue triage  │       │ • Check vs.     │       │ • Build         │
│   protocol      │       │   non-priority  │       │   leadership    │
│   adopted       │       │   cohort        │       │   summary deck  │
│ • Payer touch   │       │ • Flag any      │       │ • Set Year 1    │
│   templates     │       │   regressions   │       │   target KPIs   │
│   deployed      │       │   early         │       │                 │
└─────────────────┘       └─────────────────┘       └─────────────────┘
```

---

## 🧰 Tech Stack & Skills Demonstrated

| Category | Details |
|----------|---------|
| **Languages** | Python 3.10, SQL (PostgreSQL) |
| **Libraries** | pandas, matplotlib, numpy |
| **Analytics techniques** | KPI design, Pareto segmentation, cohort profiling, AR aging analysis |
| **Domain expertise** | Revenue cycle management, denials management, AR follow-up workflows |
| **Communication** | Decision-ready outputs framed for RevOps/RCM stakeholders |

---

## 📁 Artifacts

| Resource | Link |
|----------|------|
| 📂 Analysis repository | [stalcup-dev/revenue-cycle-healthcare-claims](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims) |
| 📖 Project README + outputs | [View README](https://github.com/stalcup-dev/revenue-cycle-healthcare-claims#readme) |
| 🗂️ Portfolio home | [Main portfolio README](../README.md) |

---

## 💼 Why This Matters to a Recruiter

> This project demonstrates more than technical SQL and Python skills. It shows the full analyst workflow that RCM and RevOps teams actually need:
>
> - **Domain fluency** — understands denial reason codes, AR aging mechanics, and how RCM operations run day-to-day
> - **Metric design from scratch** — built a KPI framework grounded in operational decision-making, not generic dashboard metrics
> - **Pareto-first thinking** — leads with concentration analysis to focus resources where impact is highest
> - **Stakeholder translation** — outputs are framed as action queues and impact models, not just charts
> - **Built-in accountability** — 30/60/90 validation plan closes the loop between analysis and measurable business delta

---

<div align="center">

*Part of the [Data Analysis Portfolio](../README.md) by stalcup-dev*

</div>
