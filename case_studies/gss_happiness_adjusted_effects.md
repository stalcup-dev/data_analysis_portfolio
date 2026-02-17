# GSS Happiness — Adjusted Effects (Survey Inference)

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![Survey Inference](https://img.shields.io/badge/Domain-Survey_Inference-3b82f6?style=flat)

## TL;DR
- Estimated adjusted (model-standardized) differences in P(VERY HAPPY) across key predictors (health, income position, marital status).
- Added inference guardrails: WTSSPS-weighted descriptives, documented limitations (non-causal framing, survey design caveats), and sensitivity notes.
- Made results reproducible with phase-based scripts, saved figures/tables, and unit tests for preprocessing rules.

## Business Question
Which factors are most strongly associated with being “Very happy” in recent U.S. survey data (GSS 2010–2022), after adjusting for other covariates?

## Data
- General Social Survey (GSS) extract (2010–2022) with WTSSPS survey weights.
- Notes: The repo documents a 2021–2022 survey mode change and treats results as interpretive (not causal).
- **Primary stakeholder:** Research/insights lead.
- **Time to deliver:** Self-directed portfolio sprint; iterated as findings were validated.

## Approach
- Phase 1: schema + label reporting and validation.
- Phase 2: WTSSPS-weighted descriptives (trends, crosstabs) + missingness guardrails.
- Phase 3: multinomial logit modeling (unweighted, with limitations documented) + standardized/adjusted effects plots.
- Quantify stability via respondent-level bootstrap “stability intervals” (model held fixed during resampling, WTSSPS applied when averaging predicted probabilities).

## Key Results
- Adjusted P(VERY HAPPY): Excellent vs Poor health = +4.6 pp (bootstrap stability interval 4.56–4.59 pp).
- Income position (within-year quartiles): Q4 vs Q1 = +2.6 pp (2.63–2.64 pp).
- Marital status: Married vs Divorced = +2.9 pp (2.90–2.91 pp).
- Predictive lift is minimal (log loss: baseline 1.0329 ± 0.0018 vs core 1.0359 ± 0.0037), so results are positioned as interpretive rather than classification.

(Results sourced from the project repo README.)

## So What (Decision / Impact)
- Demonstrates how I present adjusted effects with explicit guardrails (associations, not causality) and transparent limitations.
- Provides a reproducible template for survey-style analysis: validation → weighted descriptives → adjusted comparisons → documented interpretation policy.

## Artifacts
- Repo: https://github.com/stalcup-dev/gss-happiness-adjusted-effects
- Primary artifact: https://github.com/stalcup-dev/gss-happiness-adjusted-effects/blob/main/INSIGHTS.md
- How to verify:
  - Follow the repo download/setup instructions (see `docs/DOWNLOAD_GSS.md`).
  - Run the phase scripts (Phase 1–3) to regenerate `reports/figures` and `reports/tables`.
  - Run tests to confirm preprocessing/validation guardrails.
  - Tests/CI: see `tests/` and `.github/workflows/ci.yml` in the repo for automated checks of preprocessing and modeling steps.

## Tech + Skills Demonstrated
- Survey-aware analytics: weighting in descriptives, documented design limitations
- Inference communication: adjusted effects + non-causality guardrails
- Reproducibility: scripted pipeline + saved artifacts + unit tests
