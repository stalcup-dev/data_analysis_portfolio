# Allen Stalcup – Data Analytics Portfolio

## About

Hi, I’m Allen 👋

I’m a **Medical Laboratory Technician (8+ years)** pivoting into **Data Analytics / BI**, with a focus on:

- **A/B testing** (effect sizes, confidence intervals, practical significance)
- **Healthcare & lab operations** (QC, Westgard rules, TAT, SLA, bench/instrument performance)
- **Revenue, forecasting, and operations** for **e-commerce and small businesses**
- **Automation & local AI tools** to reduce manual busy work and protect data privacy

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=flat&logo=postgresql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-Data_Visualization-F2C811?style=flat&logo=powerbi&logoColor=black)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare_Analytics-00AEEF?style=flat)
![Remote](https://img.shields.io/badge/Open_to-Remote_Work-6cc24a?style=flat)

## Skills (evidence)

| Skill | Evidence in this portfolio |
|---|---|
| A/B testing, inference, CIs | A/B Marketing Experiment — Ad vs PSA |
| SQL analytics (CTEs, time logic) | Lab Operations SLA & QC Analytics |
| BI + stakeholder dashboards | Power BI Dashboard / KPI Dashboard |
| Data modeling (star schema / marts) | Forecasting + KPI Dashboard (dbt + warehouse) |

In the lab, I’ve spent years making sure high-stakes results are **accurate, timely, and audit-ready**. Now I use **SQL, Python, and Power BI** to do the same for data: build pipelines, calculate meaningful metrics, and turn them into dashboards decision-makers can use.

This repository/README is my central hub to:

- Showcase my **end-to-end analytics projects**
- Track my learning in **data analytics, BI, and automation**
- Demonstrate how I combine **domain expertise (lab + health + operations)** with modern data tools

### Career path (short version)

- 2017–Present → Medical Laboratory Technologist – Core Lab / Chemistry / QC / Microbiology (high-stakes ops, accuracy, audit-ready reporting)  
- 2019–Present → Running an **Amazon + eBay reselling business** (4+ years): sourcing, pricing/margins, inventory/reorder planning, listing optimization, fulfillment/returns, **basic paid marketing**, and performance tracking  
- 2023–2024 → Started formal training in **Python, SQL, statistics, and data analysis**  
- 2024–2025 → Built **healthcare ops + experimentation + e-commerce analytics projects** in SQL, Python, dbt, and Power BI  
- Now → Targeting **remote Data Analyst / BI** roles (product/growth experimentation, healthcare ops, e-commerce/ops analytics)

---

## Table of contents
- [About](#about)
- [Skills (evidence)](#skills-evidence)
- [Project Index (quick scan)](#project-index-quick-scan)
- [Featured Projects](#featured-projects)
- [Portfolio Projects](#portfolio-projects)
  - [Experimentation (A/B Testing)](#experimentation-ab-testing)
  - [Healthcare & Lab Operations](#healthcare--lab-operations)
  - [E-commerce & Forecasting](#e-commerce--forecasting)
  - [Machine Learning & Modeling](#machine-learning--modeling)
  - [Tools & Automation](#tools--automation)
- [Study Projects](#study-projects)
- [Skills & Tools](#skills--tools)
- [Certificates & Coursework](#certificates--coursework)
- [Contacts](#contacts)


---

## Project Index (quick scan)

| Project | What it proves | Stack | Link |
|---|---|---|---|
| A/B Marketing Experiment — Ad vs PSA | Experiment design → inference → ship/no-ship recommendation | Python, statsmodels | <[AB_REPO_LINK](https://github.com/stalcup-dev/marketing-ab-experiment)> |
| Sales Forecasting & KPI Dashboard | End-to-end analytics + BI delivery | Postgres, dbt, Python, Power BI | <[LINK](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl)> |
| Lab SLA & QC Analytics | Ops metrics, SQL depth, audit-ready thinking | SQL, Postgres, Python | <[LINK](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis)> |

---

## Featured Projects 

### 1) A/B Marketing Experiment — Ad vs PSA (Experimentation + Decision Memo)
**Business question:** Should we replace the PSA (control) with the product Ad (treatment) to increase purchases?

**Primary metric:** Conversion to purchase (binary)

**Headline result:** Replacing PSA with the Ad increases conversion from **1.79% → 2.55%** (**+0.76 pp**, ~**+42%** relative lift).

[![Conversion rate by group (95% CI)](https://raw.githubusercontent.com/stalcup-dev/marketing-ab-experiment/main/visuals/conversion_rate_by_group_95CI.png)](https://github.com/stalcup-dev/marketing-ab-experiment/blob/main/visuals/conversion_rate_by_group_95CI.png)


**What I built (deliverables):**
- **Experiment readout**: conversion summary, absolute/relative lift, and confidence intervals
- **Validity checks**: sample size sanity, practical vs statistical significance framing
- **Cohort cuts**: lift by **ad intensity** and **day-of-week behavior** to explain *where* lift comes from
- **Model-based estimate (optional)**: logistic regression to estimate treatment effect while controlling for exposure/usage signals
- **Decision memo**: “ship / don’t ship” recommendation with business impact framing

**Tech stack:** Python (pandas, statsmodels), SQL/dbt (feature marts/cohorts), Jupyter, Git/GitHub

**Repository**
**Repository:** [`marketing-ab-experiment`](https://github.com/stalcup-dev/marketing-ab-experiment)  
**Notebooks:** https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/notebooks  

---

## Featured Projects 

### 1) A/B Marketing Experiment — Ad vs PSA (Experiment Integrity + Decision Pack)
**Business question:** Should we replace the PSA (control) with the product Ad (treatment) to increase purchases?

**Primary metric:** Conversion to purchase (binary)

**Headline result:** Replacing PSA with the Ad increases conversion from **1.79% → 2.55%** (**+0.77 pp**, ~**+43%** relative lift).  
**Uncertainty:** 95% CI for lift ≈ **[+0.60, +0.94] pp** (directional on this dataset).  
**Business framing:** ≈ **7,692** incremental conversions per **1M** exposures (using +0.769 pp).

[![Conversion rate by group (95% CI)](https://raw.githubusercontent.com/stalcup-dev/marketing-ab-experiment/main/visuals/conversion_rate_by_group_95CI.png)](https://github.com/stalcup-dev/marketing-ab-experiment/blob/main/visuals/conversion_rate_by_group_95CI.png)

**What I built (deliverables):**
- **Experiment integrity report**: SRM check + baseline QA + group balance diagnostics before trusting results
- **Estimation report**: conversion summary, absolute/relative lift, p-values, and **95% confidence intervals**
- **Robustness checks**: **stratified lift by day/hour** vs naive lift to test whether timing mix explains the effect
- **Cohort cuts**: lift by **ad intensity** and **day-of-week behavior** to explain *where* lift comes from
- **Model-based estimate (optional)**: logistic regression to estimate treatment effect while controlling for exposure/usage signals
- **1-page decision memo**: “ship / don’t ship” recommendation with impact framing + risk/assumption callouts
- **Reproducibility & quality**: report builder scripts + **pytest** checks + linting (ruff) for a work-ready workflow

**Tech stack:** Python (pandas, statsmodels), SQL/dbt (feature marts/cohorts), Jupyter, Git/GitHub

**Links:**  
- **Repo:** [`marketing-ab-experiment`](https://github.com/stalcup-dev/marketing-ab-experiment)  
- **Notebooks:** https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/notebooks  
- **Reports:** https://github.com/stalcup-dev/marketing-ab-experiment/tree/main/decision_pack/reports


#### 2. Chemistry QC Automation & Westgard Rules
**Repository:** [`chemistry-qc-automation`](https://github.com/stalcup-dev/chemistry-qc-automation)  

**Description:**  
Automation of **clinical chemistry QC data** aggregation and Westgard rule evaluation.

**What this shows:**

- Parsing and aggregating QC data programmatically
- Implementing **Westgard rule logic** to automatically flag failures
- Generating **audit-ready outputs** for lab inspections and troubleshooting
- Bridges my **lab QC domain knowledge** with **Python automation**

**Tech stack:** Python (pandas), QC logic, automation scripts.

---

### E-commerce & Forecasting

#### 3. End-to-End Sales Forecasting & KPI Dashboard (ETL + BI)
**Repository:** [`end-to-end-sales-forecasting-kpi-dashboard-etl`](https://github.com/stalcup-dev/end-to-end-sales-forecasting-kpi-dashboard-etl)  

**Description:**  
End-to-end analytics workflow for an e-commerce-style dataset: **ETL, forecasting, and KPI dashboard**.

**What this shows:**

- **Data modeling** in a warehouse (Postgres) with layered schemas
- **dbt** transformations for clean, reusable models
- **Prophet** forecasting for SKU-level or category-level sales
- Power BI dashboard with **KPI cards, trends, and drill-downs** for business users

**Tech stack:** PostgreSQL, dbt, Python (pandas, Prophet), Power BI(DAX), SQL.


#### 4. E-commerce Power BI Dashboard
**Repository:** [`ecommerce-powerbi-dashboard`](https://github.com/stalcup-dev/ecommerce-powerbi-dashboard)  

**Description:**  
Star-schema-based **Power BI dashboard** for e-commerce performance.

**What this shows:**

- Designing a **fact + dimension model** for analytics
- Writing **DAX measures** for revenue, AOV, retention, and other business KPIs
- Producing **stakeholder-ready visuals** for non-technical decision-makers

**Tech stack:** Power BI, DAX, data modeling, basic SQL / ETL.

---

### Machine Learning & Modeling

#### 5. Insurance Cost Analysis (Regression Modeling)
**Repository:** [`insurance-cost-analysis`](https://github.com/stalcup-dev/insurance-cost-analysis)  

**Description:**  
Real-world, regression-based ML project predicting **medical insurance charges** and explaining cost drivers. A course project taken a few steps further in normalizing the data and validating with R², MAE, RMSE.

**What this shows:**

- Data cleaning and **feature engineering**  
- Training and evaluating regression models  
- Interpreting model outputs to answer:  
  > “Which factors most strongly drive insurance charges, and how could a business act on this?”  
- Communication of results in **business-friendly language**

**Tech stack:** Python (pandas, scikit-learn), regression modeling, visualization (matplotlib/other).

---

### Tools & Automation

#### 6. Local AI Privacy Control – Offline Document Assistant
**Repository:** [`local-ai-privacy-control`](https://github.com/stalcup-dev/local-ai-privacy-control)  

**Description:**  
A **fully offline, GUI-based AI assistant** to analyze local Word/Excel files without sending data to the cloud.

**What this shows:**

- Practical focus on **data privacy** and local inference
- Wiring up a **user-friendly interface** to AI models
- Applying AI to **day-to-day analytics tasks** (document review, summary, quick analysis)

**Tech stack:** Python, local LLM (e.g., Llama-3), GUI framework (see repo for details).


#### 7. Extracting and Visualizing Stock Data
**Repository:** [`Extracting-and-Visualizing-Stock-Data`](https://github.com/stalcup-dev/Extracting-and-Visualizing-Stock-Data)  

**Description:**  
End-to-end mini-project extracting stock and revenue data (e.g., Tesla, GameStop) and visualizing trends.

**What this shows:**

- Pulling data from the web / APIs (e.g., `yfinance` / scraping)
- Using **pandas** for time-series manipulation
- Plotting **price vs revenue** and exploring basic relationships

**Tech stack:** Python, pandas, Plotly/matplotlib, basic web data acquisition.

---

### Experimentation (A/B Testing)

#### 8. A/B Marketing Experiment — Ad vs PSA
**Repository:** [`marketing-ab-experiment`](https://github.com/stalcup-dev/marketing-ab-experiment)

---

## Study Projects

This section tracks work from courses, guided projects, and structured learning.

### Python & Data Analysis

- **Python for Everybody (Coursera)**  
  Foundations of Python, data structures, APIs, and basic data processing.  
  Status: **Completed**

- **Extracting and Visualizing Stock Data with Python**  
  Part of an applied data science track: web data extraction (e.g., `yfinance`) and visualization of financial metrics.  
  Status: **Completed / In use in this repo** → [`Extracting-and-Visualizing-Stock-Data`](https://github.com/stalcup-dev/Extracting-and-Visualizing-Stock-Data)

### Data Analytics & BI

- **IBM Data Analyst Professional Certificate (Coursera)**  
  SQL, Excel, Python, and dashboarding for data analytics.  
  Status: **In progress**

- **Power BI / PL-300 Prep**  
  Building data models, DAX, and reports aligned to PL-300 exam competencies.  
  Status: **In progress** (applied in [`ecommerce-powerbi-dashboard`](https://github.com/stalcup-dev/ecommerce-powerbi-dashboard))

### Algorithms, Foundations & Other

- Ongoing self-study in:
  - SQL (window functions, CTEs, performance considerations)
  - Basic statistics and experiment analysis
  - Best practices for **data quality, validation, and documentation**

---

## Skills & Tools

### Analytics & BI

- **SQL** – joins, CTEs, aggregations, window functions, SLA/TAT calculations
- **Power BI** – star schema modeling, DAX, KPI dashboards, stakeholder-ready reports
- **Excel** – pivot tables, basic analytics, quick QA checks

### Programming & Data

- **Python** – pandas, numpy, matplotlib/Plotly, scikit-learn, Seaborn, Prophet (forecasting)
- Data wrangling, feature engineering, time-series and regression modeling
- Basic automation for **data pipelines and QC routines**

### Domain Expertise

- **Clinical lab operations** – chemistry, microbiology, toxicology, QC, Westgard rules; audit-ready documentation and process control
- **Operational performance metrics** – turnaround time (TAT), SLA compliance, bottleneck analysis, instrument/bench-level performance, LIS-style workflows
- **E-commerce (Amazon + eBay resale, 4+ years)** – product sourcing and selection, pricing and margin control, inventory and reorder planning, listing optimization (titles/keywords/photos), order fulfillment and shipping workflows, returns/refunds management, and performance metrics (sell-through rate, profit per unit, fees/COGS, break-even price)


### Work Style

- Comfortable in **async / remote** environments
- Thinks in **metrics and processes**: “What should we measure?”, “How do we improve it?”
- Bridges **subject-matter expertise + data**: not just charts, but decisions

---

## Certificates & Coursework

- **Python for Everybody – Coursera** (Completed)  
- **IBM Data Analyst Professional Certificate – Coursera** (In progress 90% complete)  
- Additional certificates and badges to be added as completed.

---

## Contacts

I’m open to **remote Data Analyst / BI** roles.

- **GitHub:** [@stalcup-dev](https://github.com/stalcup-dev)   
- **Email:** _(allen.stalc@gmail.com)_

If you’d like to talk about my projects or potential collaboration, feel free to reach out.
