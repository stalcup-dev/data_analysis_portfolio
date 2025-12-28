# Sales Forecasting & KPI Dashboard (Vita Markets)

## TL;DR
- Built a reproducible pipeline from raw CSV → PostgreSQL → dbt models → Prophet forecasts → Power BI dashboards.
- Reported forecast quality using a holdout set (MAPE, bias, coverage) and exposed results via stable database views for BI.
- Generated inventory-facing purchase recommendations using lead time demand + safety stock + on-hand inventory.

## Business Question
How can we turn raw sales data into refreshable KPIs and trustworthy forecasts for planning, reporting, and reorder decisions?

## Data
- Source: Synthetic DTC retailer dataset (Vita Markets) described in the project repo.
- Notes: This is a portfolio simulation; insights are for demonstration.

## Approach
- Model the warehouse in Postgres + dbt (staging → marts) to support consistent KPIs.
- Generate SKU-level time series forecasts using Prophet with train/test evaluation.
- Publish forecasts + accuracy metrics as stable SQL views so Power BI can refresh without pointing at versioned tables.
- Produce reorder recommendations from:
  - 14-day lead time demand forecast
  - 90% service level safety stock (z=1.28)
  - Current on-hand inventory
  - Forecast confidence (MAPE-based rating)

## Key Results (verified)
From the project README:
- Automated reporting reduced manual effort from **4 hours/week → 0 hours**.
- Forecasting performance summary: **Median MAPE 12.3%**, **Coverage ~80%**, **Bias ~0**.
- Example business narrative includes **150% YoY growth** for a “New Launch” SKU and **25% YoY growth** for “Flagship Growth”.

Source: https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl#-key-business-insights

## So What (Decision / Impact)
- Shows end-to-end delivery: modeling + evaluation + stakeholder-facing dashboards, with a clear contract between data products (views) and BI.
- Demonstrates “forecasting for action” (inventory planning) rather than forecasting as a standalone model.

## Artifacts
- Repo: https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl
- Dashboard previews:
  - KPI dashboard: https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/KPIDashboard.png
  - Forecasting dashboard: https://raw.githubusercontent.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl/main/ForecastingDash.png
- How to verify:
  - Follow the repo “Quick Start (10 minutes)” instructions.
  - Use the repo “Verification Checklist” to confirm forecast rows, metrics, and view schemas.
  - Tests/CI: see `.github/workflows/ci.yml` and `tests/` in the repo for automated checks of models and pipelines.

## Tech + Skills Demonstrated
- Data modeling: PostgreSQL + dbt (staging/marts, schema tests)
- Forecasting: Prophet + train/test evaluation (MAE/RMSE/MAPE/bias/coverage)
- BI delivery: Power BI (KPIs, forecast vs actuals with uncertainty bands)
- Reliability: stable data contract for BI + automated checks/CI in the project repo
