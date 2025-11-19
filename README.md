# Allen Stalcup – Data Analytics Portfolio

## About

Hi, I’m Allen 👋

I’m a **Medical Laboratory Technician (8+ years)** pivoting into **Data Analytics / BI**, with a focus on:

- **Healthcare & lab operations** (QC, Westgard rules, TAT, SLA, bench/instrument performance)
- **Revenue, forecasting, and operations** for **e-commerce and small businesses**
- **Automation & local AI tools** to reduce manual busy work and protect data privacy

In the lab, I’ve spent years making sure high-stakes results are **accurate, timely, and audit-ready**. Now I use **SQL, Python, and Power BI** to do the same for data: build pipelines, calculate meaningful metrics, and turn them into dashboards decision-makers can use.

This repository/README is my central hub to:

- Showcase my **end-to-end analytics projects**
- Track my learning in **data analytics, BI, and automation**
- Demonstrate how I combine **domain expertise (lab + health + operations)** with modern data tools


### Career path (short version)

- 2017–2023 → Medical Laboratory Technologist – Core Lab / Chemistry / QC / Microbiology  
- 2023–2024 → Started formal training in **Python, SQL, and data analysis**  
- 2024–2025 → Built **healthcare, QC, and e-commerce analytics projects** in SQL, Python, dbt, and Power BI  
- Now → Targeting **remote Data Analyst / BI** roles (healthcare, operations, e-commerce, or technical teams that value domain experts who can work with data)

---

## Table of contents

- [About](#about)  
- [Portfolio Projects](#portfolio-projects)  
  - [Healthcare & Lab Operations](#healthcare--lab-operations)  
  - [E-commerce & Forecasting](#e-commerce--forecasting)  
  - [Machine Learning & Modeling](#machine-learning--modeling)  
  - [Tools & Automation](#tools--automation)  
- [Study Projects](#study-projects)  
- [Skills & Tools](#skills--tools)  
- [Certificates & Coursework](#certificates--coursework)  
- [Contacts](#contacts)

---

## Portfolio Projects

### Healthcare & Lab Operations

#### 1. Lab Operations SLA & QC Analytics (SQL)

**Repository:** [`sql-lab-insights-and-sla-analysis`](https://github.com/stalcup-dev/sql-lab-insights-and-sla-analysis)  

**Description:**  
SQL-driven analysis of **laboratory performance metrics**, including turnaround time, test volume, and SLA performance.

**What this shows:**

- Calculation of **SLA metrics** (on-time vs delayed results) using SQL
- Identification of **bottlenecks** by test, bench, or instrument
- Breakdown of performance across **time of day / day of week**
- Focus on metrics a **lab manager, QA lead, or operations director** would actually use

**Tech stack:** PostgreSQL (or other RDBMS), SQL (CTEs, aggregations, date/time logic).


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

**Tech stack:** PostgreSQL, dbt, Python (pandas, Prophet), Power BI, SQL.


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

- **Clinical lab operations** – chemistry, microbiology, toxicology, QC, Westgard rules
- **Turnaround time & SLA/ Calculated KPI metrics**, instrumentation, LIS workflows
- **Lab Data** Built queries to save time and managed messy datasets in lab. 

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
