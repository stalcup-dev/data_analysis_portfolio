# A/B Marketing Experiment — Ad vs PSA

## TL;DR
- Built an experiment “decision pack” that runs integrity checks (SRM/balance) before estimating lift and generating a 1-page memo.
- Reported directional lift with confidence intervals, plus robustness checks (stratified by time).
- Packaged outputs as reproducible Markdown reports for stakeholder review.

## Business Question
Should we replace the PSA (control) with a product Ad (treatment) to increase purchases?

## Data
- Source: Kaggle `marketing_AB` dataset (see repo README for details).
- Notes: The full CSV is intentionally not committed; the repo uses a small fixture for CI.

## Approach
- Integrity checks: traffic allocation diagnostic (SRM vs expected split), basic QA, and timing distribution diagnostics.
- Estimation: conversion rates, absolute/relative lift, hypothesis test and confidence interval.
- Robustness: stratified lift by day/hour to test whether timing mix explains the effect.
- Communication: a short decision memo that explicitly separates “directional evidence” vs “causal estimate” given allocation imbalance.

## Key Results
- See the repo Executive Summary / Key Results for the verified metrics and caveats: https://github.com/stalcup-dev/marketing-ab-experiment#executive-summary

## So What (Decision / Impact)
- Demonstrates how I would prevent teams from over-trusting a lift estimate when integrity checks indicate the data does not resemble a classic randomized 50/50 A/B.
- The decision pack format supports a practical ship/no-ship recommendation backed by documented assumptions and reproducible outputs.

## Artifacts
- Repo: https://github.com/stalcup-dev/marketing-ab-experiment
- Primary artifact: https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports
- How to verify:
  - Follow the repo “Reproduce the Decision Pack (reports)” instructions.
  - Shortcut links:
    - `decision_memo_1pager.md`: https://github.com/stalcup-dev/marketing-ab-experiment/blob/main/decision_pack/reports/decision_memo_1pager.md
    - `integrity_report.md`: https://github.com/stalcup-dev/marketing-ab-experiment/blob/main/decision_pack/reports/integrity_report.md
    - `estimation_report.md`: https://github.com/stalcup-dev/marketing-ab-experiment/blob/main/decision_pack/reports/estimation_report.md

## Tech + Skills Demonstrated
- Experimentation analytics: SRM/balance checks, lift + CI, robustness analysis
- Analytics engineering: reusable code to generate consistent reports
- Stakeholder communication: decision memo with explicit uncertainty and caveats
