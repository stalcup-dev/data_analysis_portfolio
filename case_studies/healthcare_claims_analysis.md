# Healthcare Claims Analysis

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_Analytics-00AEEF?style=flat)

## TL;DR
- Built a reproducible claims analysis pipeline that generates clean data, KPI tables, figures, and written outputs.
- Rendered a decision memo and a data dictionary directly from pipeline outputs (no hand-typed metrics).
- Included ingestion QA checks (missingness/ranges/uniqueness) so outputs are audit-ready.

## Business Question
What are the headline claims KPIs, cost concentration signals, and “where to look next” insights we can summarize in a decision memo?

## Data
- Synthetic claims dataset (`claim_data.csv`) used for portfolio demonstration.
- Notes: Results reflect this synthetic sample; real claims typically show stronger skew/cost concentration.
- **Primary stakeholder:** Revenue cycle analyst / finance operations lead.
- **Time to deliver:** TBD (self-paced; replace with actual delivery time).

## Approach
- Orchestrate an end-to-end run (load → quality checks → cleaning → metrics/analysis → doc rendering).
- Compute KPI summaries (billed totals, distribution stats) and concentration (Pareto) from pipeline outputs.
- Auto-generate documentation artifacts (README tables, decision memo, data dictionary) from the same output tables.

## Key Results
- Total claims: 1,000; Total billed: $297,191.00; P95 claim: $480.00.
- Cost concentration: Top 10% of patients account for 16.12% of total cost.
- Top diagnosis by spend: A05.4 at 1.98% of total billed.

(Results sourced from the project repo README.)

## So What (Decision / Impact)
- Demonstrates an “analytics product” pattern: pipeline outputs → decision memo → documented assumptions and definitions.
- The data dictionary + reproducible outputs reduce ambiguity and rework when stakeholders ask “how was this computed?”

## Artifacts
- Repo: https://github.com/stalcup-dev/healthcare-claims-analysis
- Primary artifact: https://github.com/stalcup-dev/healthcare-claims-analysis/blob/main/docs/decision_memo.md
- How to verify:
  - Run the full pipeline: `python -m scripts.run_all`
  - Confirm generated outputs exist (tables/figures/reports) and that docs are sourced from outputs (e.g., decision memo + data dictionary).

## Tech + Skills Demonstrated
- Python analytics pipeline design (pandas/numpy)
- Data quality checks + audit-ready metric definitions
- Reproducible reporting: generated docs (memo + data dictionary) tied to pipeline outputs
