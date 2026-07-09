# HEDIS & Stars Quality Performance Control Room — Design Document

**Project name:** HEDIS & Stars Quality Performance Control Room  
**Repository name recommendation:** `hedis-stars-quality-control-room`  
**Design version:** v0.1  
**Primary purpose:** Hiring artifact + case study + reusable healthcare quality analytics product pattern  
**Primary target roles:** HEDIS Data Analyst, Population Health Data Analyst, Quality Improvement Data Analyst, Healthcare Data Analyst, Healthcare Data Quality Analyst, EHR Data Analyst, Health IT Data Analyst, Stars / Quality Analyst, Care Gap Analyst, Provider Performance Analyst

---

## 1. Project Summary

Build a public-safe healthcare quality analytics system that combines:

1. **Real CMS Part C / D Star Ratings performance data** for plan-level quality benchmarking.
2. **Real CDC BRFSS public survey data** for population-health and preventive-screening context.
3. **Synthetic member-level claims, EHR, screening, outreach, and evidence data** for care-gap operations.

The app should simulate the workflow a payer, provider group, quality team, or population health team would use to move from quality measurement to operational action.

The final product should answer:

- Which plans / contracts / measures are underperforming?
- Which preventive-care or quality-measure gaps appear in public population data?
- Which synthetic members have open care gaps?
- Which gaps should be worked first?
- Which data sources are missing evidence?
- How many gap closures are needed to reach target performance?
- What should be included in an executive decision pack?

---

## 2. Why This Project Exists

The existing Revenue Integrity project already covers:

- owner-routed queues
- failed controls
- blockers
- recoverability
- exception logic
- workflow intelligence
- financial risk

This HEDIS / Stars project should create a **second portfolio pillar**:

| Existing pillar | New pillar |
|---|---|
| Revenue Integrity / RCM | HEDIS / Stars / Population Health |
| Revenue leakage | Care gaps |
| Recoverability | Measure performance |
| AR / denial risk | Quality / Stars / HEDIS performance |
| Billing action queues | Outreach action queues |
| Failed revenue controls | Missing evidence / data completeness |
| Financial action | Clinical quality action |

The new project should replace the older Lab SLA project as the lead proof inside the **Healthcare Data Quality / EHR Workflow** role packet. The lab project can remain as supporting evidence of clinical workflow literacy.

---

## 3. Important Compliance / Honesty Notes

This project must be explicitly public-safe.

### Do not claim:

- access to private HEDIS submissions
- access to real patient-level HEDIS data
- reproduction of proprietary NCQA technical specifications
- audited HEDIS measure certification
- official health-plan performance calculations beyond what is publicly available

### Do claim:

- uses real public CMS Star Ratings data for external plan-level quality context
- uses real public CDC BRFSS survey data for population-health context
- uses synthetic member-level data to demonstrate care-gap operations
- uses HEDIS-inspired measure logic for portfolio demonstration
- focuses on measure logic, data completeness, care gap detection, outreach prioritization, and decision support

Recommended README disclaimer:

> This project is HEDIS-inspired and public-safe. It does not reproduce proprietary NCQA technical specifications or use private patient/member data. Real CMS and CDC public datasets are used for benchmark/context layers, while synthetic member-level data is used to demonstrate operational care-gap workflows.

---

## 4. Real Public Data Sources

### 4.1 CMS Part C and D Performance Data

Use CMS Part C and D Performance Data as the real plan-quality benchmark layer.

CMS states that the page contains performance data related to Part C & D programs, and the downloads include 2026 Star Ratings Data Tables, 2025 Star Ratings Data Tables, 2024 Star Ratings Data Tables, technical notes, display measures, and historical ZIP files.

Source:

- https://www.cms.gov/medicare/health-drug-plans/part-c-d-performance-data

Expected use:

| Use case | Data role |
|---|---|
| Stars benchmark view | Compare contracts/plans by available Star Ratings fields |
| Measure opportunity view | Identify underperforming measures/contracts |
| Trend view | Compare historical years where available |
| Case-study credibility | Show real payer-quality context |

Implementation notes:

- Start with the most recent available Star Ratings data tables.
- Store the raw ZIP or extracted CSV/XLSX files under `data/raw/cms_star_ratings/`.
- Build a parser that standardizes file names, sheet names, contract IDs, measure names, ratings, and year.
- If CMS files are Excel-based, use `openpyxl` or `pandas.read_excel`.
- If the files are CSV inside ZIPs, use Python `zipfile` and `pandas.read_csv`.

---

### 4.2 CDC BRFSS Annual Survey Data

Use BRFSS as the public population-health context layer.

CDC provides BRFSS annual survey data and documentation by year. The documentation includes technical and statistical information such as comparability and sample information, with annual survey data available through 2024 on the CDC page.

Source:

- https://www.cdc.gov/brfss/annual_data/annual_data.htm

Expected use:

| Use case | Data role |
|---|---|
| Preventive screening context | Show screening / preventive-care gaps by state or demographic group |
| Public health benchmark | Add population context behind care gaps |
| Case-study credibility | Demonstrate use of a serious public health dataset |
| Optional expansion | Compare screening proxy patterns to synthetic member opportunities |

Implementation notes:

- Start with **2024 BRFSS** if feasible.
- If 2024 file size is too heavy for first build, use a smaller extracted subset or state-level aggregate from CDC tools.
- Focus on variables that support preventive-care / women’s health / screening context.
- BRFSS is survey-based. It should not be treated as member-level EHR/claims data.

---

### 4.3 NCQA ECDS Public Context

Use NCQA’s public ECDS page to guide project vocabulary, measure selection, and data-source categories.

NCQA describes ECDS reporting as a HEDIS reporting method where clinical data can create insight for managing the health of individuals and groups. The page lists ECDS-related measure categories such as behavioral health, preventive screening, immunizations, health equity, and chronic-condition management.

Source:

- https://www.ncqa.org/resources/hedis-electronic-clinical-data-systems-ecds-reporting/

Relevant public concepts to mirror:

| Concept | Project mapping |
|---|---|
| EHR / PHR source category | Synthetic EHR events and screening records |
| HIE / clinical registry source category | Synthetic registry evidence table |
| Case management source category | Synthetic outreach / case management table |
| Administrative source category | Synthetic claims and eligibility table |
| Preventive screening measures | Breast, colorectal, cervical screening |
| Behavioral health measures | Prenatal / postpartum depression screening and follow-up |
| Digital quality transition | Data completeness and evidence-source confidence |

Important: do not copy proprietary measure specs. Use public measure names and HEDIS-inspired logic.

---

## 5. Project Scope

### MVP Scope

Build a Streamlit-first app with deterministic backend logic and exported artifacts.

MVP includes:

1. CMS Star Ratings benchmark ingestion and summary.
2. BRFSS preventive screening context ingestion or curated sample.
3. Synthetic member-level data generator.
4. HEDIS-inspired measure logic engine.
5. Member-level care gap queue.
6. Data completeness audit.
7. Gap closure impact simulator.
8. Exportable decision pack.
9. Case study markdown.
10. Tests for measure logic and data quality.

### Non-goals for MVP

- Full official HEDIS implementation.
- Full NCQA specification reproduction.
- Private patient/member data.
- Live payer/EHR API integrations.
- Complex ML prediction.
- Full FHIR server implementation.
- Production authentication.
- Perfect visual polish before the case study exists.

---

## 6. MVP Measures

Start with 5 measures.

| Measure ID | Measure name | Domain | Reason for inclusion |
|---|---|---|---|
| `BCS_SIM` | Breast Cancer Screening | Preventive screening | Strong HEDIS / Stars / women’s health relevance |
| `CCS_SIM` | Cervical Cancer Screening | Preventive screening | OBGYN tie-in and ECDS relevance |
| `COL_SIM` | Colorectal Cancer Screening | Preventive screening | Broad population health measure |
| `PND_SIM` | Prenatal Depression Screening and Follow-Up | Behavioral health / OBGYN | Strong outpatient OBGYN workflow tie-in |
| `PDS_SIM` | Postpartum Depression Screening and Follow-Up | Behavioral health / OBGYN | Strong care-gap and follow-up story |

Optional v2 measures:

| Measure ID | Measure name | Why add later |
|---|---|---|
| `BPD_SIM` | Blood Pressure Control for Patients With Diabetes | Chronic disease / ECDS direction |
| `AIS_SIM` | Adult Immunization Status | Preventive care / immunization data sources |
| `SNS_SIM` | Social Needs Screening and Intervention | Health equity / population health |

---

## 7. User Personas

### 7.1 Quality Improvement Manager

Needs to know:

- Which measures are below target?
- Which gaps should outreach work first?
- Which measures are closest to target?
- What will happen if the team closes 50, 100, or 200 gaps?

### 7.2 HEDIS / Stars Analyst

Needs to know:

- Denominator count.
- Numerator count.
- Gap count.
- Exclusions.
- Evidence source.
- Data completeness risk.
- Measure trend / benchmark context.

### 7.3 Population Health Analyst

Needs to know:

- Which populations have screening gaps?
- How do gaps vary by age, state, insurance, income, or other available BRFSS variables?
- How should outreach be prioritized?

### 7.4 EHR / Health IT Data Analyst

Needs to know:

- Which data source is missing evidence?
- Are events coming from claims, EHR, registry, outreach, or supplemental evidence?
- Are there orphan records, duplicates, missing IDs, or inconsistent dates?

---

## 8. App Views / Screens

### View 1 — Executive Summary

Purpose: first screen for a recruiter or manager.

Cards:

- Total synthetic members.
- Measures evaluated.
- Total open care gaps.
- Highest-risk measure.
- Measures below target.
- Data completeness risk count.
- Gap closures needed to hit target.

Charts:

- Measure rates vs target.
- Gap count by measure.
- Gap priority distribution.
- Evidence source completeness by measure.

Table:

| Measure | Eligible | Compliant | Open gaps | Current rate | Target | Gap to target |
|---|---:|---:|---:|---:|---:|---:|
| Breast Cancer Screening | 1,920 | 1,421 | 499 | 74.0% | 80.0% | 116 closures |

---

### View 2 — CMS Stars Benchmark

Purpose: real plan-level quality context.

Inputs:

- CMS Star Ratings file(s).
- Contract / plan fields.
- Measure ratings and overall ratings where available.

Filters:

- Year.
- Contract ID.
- Parent organization.
- State / geography if present.
- Measure category.
- Rating band.

Outputs:

- Count of contracts by rating.
- Contracts below threshold.
- Measures with most underperformance.
- Year-over-year movement if historical data is loaded.

Recruiter message:

> This project does not only simulate care gaps. It also grounds the quality story in real CMS Star Ratings performance data.

---

### View 3 — BRFSS Population Context

Purpose: public health / preventive screening context.

Inputs:

- BRFSS annual data or curated aggregate/subset.
- Survey variables related to preventive screening or access.

Filters:

- Year.
- State.
- Age group.
- Sex.
- Income / insurance / education if used.

Outputs:

- Screening prevalence by state or subgroup.
- Preventive care gap proxy rates.
- Population context cards.

Important note:

BRFSS is survey-based and should not be represented as HEDIS member-level evidence.

---

### View 4 — Measure Performance

Purpose: HEDIS-inspired denominator/numerator/gap logic.

Table:

| Measure | Denominator | Numerator | Exclusions | Open gaps | Rate | Target | Gap to target |
|---|---:|---:|---:|---:|---:|---:|---:|

Details per measure:

- Denominator rule.
- Numerator rule.
- Exclusions.
- Lookback window.
- Evidence sources.
- Data completeness status.

---

### View 5 — Care Gap Queue

Purpose: operational layer.

Columns:

| Column | Description |
|---|---|
| `gap_id` | Unique care gap ID |
| `member_id` | Synthetic member ID |
| `measure_id` | Measure where gap is open |
| `measure_name` | Human-readable measure name |
| `gap_reason` | Why member is non-compliant |
| `priority` | Blocker / High / Medium / Low |
| `owner` | Outreach / Quality / Provider Relations / Data Quality / Care Team |
| `evidence_missing` | Claims / EHR / registry / outreach / supplemental |
| `days_to_deadline` | Days remaining in simulated measurement window |
| `recommended_action` | Next step |
| `status` | Open / In progress / Closed / Excluded |

Priority logic examples:

| Priority | Logic |
|---|---|
| Blocker | deadline < 14 days, high-impact measure, or positive depression screen with no follow-up |
| High | deadline < 45 days or gap closure moves measure near target |
| Medium | standard open gap with enough time remaining |
| Low | member has evidence pending, exclusion suspected, or recently contacted |

---

### View 6 — Data Completeness Audit

Purpose: healthcare data quality angle.

Checks:

- Missing member eligibility.
- Missing date of birth.
- Missing sex / age band conflicts.
- Duplicate member IDs.
- Claims without member match.
- EHR events without member match.
- Screening record missing result date.
- Depression screen positive without follow-up evidence.
- Evidence present in one source but not another.
- Supplemental evidence not mapped to measure.

Table:

| Measure | Claims evidence | EHR evidence | Registry evidence | Outreach evidence | Missing evidence risk |
|---|---:|---:|---:|---:|---|

Risk scoring:

| Risk | Example logic |
|---|---|
| High | measure below target and evidence missing from multiple source categories |
| Medium | measure near target but one key source missing |
| Low | enough evidence across source categories |

---

### View 7 — Impact Simulator

Purpose: business value.

Inputs:

- Selected measure.
- Gap closure count.
- Gap closure priority strategy.
- Target rate.

Strategies:

- Close highest priority gaps first.
- Close gaps closest to deadline.
- Close gaps with complete contact info.
- Close gaps with provider already assigned.
- Random baseline for comparison.

Outputs:

| Scenario | Gap closures | New numerator | New rate | Target met? |
|---|---:|---:|---:|---|
| Current | 0 | 1,421 | 74.0% | No |
| Close high-priority gaps | 80 | 1,501 | 78.2% | No |
| Close high + medium gaps | 130 | 1,551 | 80.8% | Yes |

---

### View 8 — Decision Pack Export

Purpose: portfolio artifact.

Export a markdown file to `outputs/decision_pack.md` containing:

- Executive summary.
- Measures below target.
- Top care gaps.
- Gap closures needed.
- Data completeness risks.
- CMS Stars benchmark context.
- BRFSS population context.
- Recommended outreach priorities.
- Assumptions and public-safe data note.

---

## 9. Proposed Data Model

### 9.1 `members.csv`

| Column | Type | Notes |
|---|---|---|
| `member_id` | string | Synthetic unique ID |
| `dob` | date | Needed for age bands |
| `sex` | string | F / M / Other / Unknown |
| `state` | string | Two-letter state |
| `county` | string | Optional |
| `line_of_business` | string | Medicare Advantage / Commercial / Medicaid simulation |
| `enrollment_start` | date | Continuous enrollment logic |
| `enrollment_end` | date | Continuous enrollment logic |
| `pcp_id` | string | Provider assignment |
| `risk_segment` | string | Low / Medium / High |
| `phone_valid` | bool | Outreach readiness |
| `portal_active` | bool | Outreach channel |

### 9.2 `claims.csv`

| Column | Type | Notes |
|---|---|---|
| `claim_id` | string | Synthetic claim ID |
| `member_id` | string | Foreign key |
| `service_date` | date | Event date |
| `claim_type` | string | Professional / facility / pharmacy |
| `procedure_code` | string | CPT/HCPCS-style simulated code |
| `diagnosis_code` | string | ICD-style simulated code |
| `place_of_service` | string | Optional |
| `provider_id` | string | Provider |
| `paid_amount` | numeric | Optional |
| `source_system` | string | claims |

### 9.3 `ehr_events.csv`

| Column | Type | Notes |
|---|---|---|
| `event_id` | string | Synthetic event ID |
| `member_id` | string | Foreign key |
| `encounter_id` | string | Synthetic encounter |
| `event_type` | string | screening / observation / diagnosis / referral / follow_up |
| `event_date` | date | Event date |
| `code_system` | string | LOINC / SNOMED / CPT simulated |
| `code` | string | Simulated code |
| `result_value` | string | positive / negative / completed / abnormal |
| `provider_id` | string | Provider |
| `source_system` | string | EHR |

### 9.4 `screenings.csv`

| Column | Type | Notes |
|---|---|---|
| `screening_id` | string | Unique ID |
| `member_id` | string | Foreign key |
| `screening_type` | string | breast / cervical / colorectal / prenatal_depression / postpartum_depression |
| `screening_date` | date | Date performed |
| `result` | string | complete / positive / negative / abnormal / unknown |
| `evidence_source` | string | claims / EHR / registry / supplemental |
| `follow_up_date` | date | Relevant for depression / abnormal results |
| `follow_up_type` | string | referral / visit / care plan / outreach |

### 9.5 `outreach.csv`

| Column | Type | Notes |
|---|---|---|
| `outreach_id` | string | Unique ID |
| `member_id` | string | Foreign key |
| `measure_id` | string | Measure |
| `outreach_date` | date | Contact date |
| `channel` | string | phone / portal / mail / SMS |
| `outcome` | string | reached / left_message / scheduled / refused / invalid_contact |
| `owner` | string | Outreach / Care Team / Provider Relations |
| `next_action_date` | date | Follow-up |

### 9.6 `measure_definitions.yaml`

Use YAML to make measure rules transparent and recruiter-readable.

Example:

```yaml
- measure_id: BCS_SIM
  name: Breast Cancer Screening - Simulated
  domain: preventive_screening
  target_rate: 0.80
  eligible_population:
    sex: F
    min_age: 50
    max_age: 74
    continuous_enrollment_months: 12
  numerator:
    event_types:
      - screening
    screening_types:
      - breast
    lookback_months: 27
    valid_results:
      - complete
  exclusions:
    - hospice
    - bilateral_mastectomy
  evidence_sources:
    - claims
    - EHR
    - registry
    - supplemental
  owner: Quality / Population Health
```

---

## 10. Measure Logic Requirements

Each measure calculation should output:

| Field | Definition |
|---|---|
| `measure_id` | Measure identifier |
| `member_id` | Member identifier |
| `eligible` | Boolean |
| `excluded` | Boolean |
| `compliant` | Boolean |
| `gap_open` | Boolean |
| `evidence_source` | Best available evidence source |
| `gap_reason` | Human-readable reason |
| `priority` | Blocker / High / Medium / Low |
| `owner` | Responsible queue |
| `recommended_action` | Next step |

Generic rate formula:

```text
rate = compliant_count / (eligible_count - exclusion_count)
```

Gap-to-target formula:

```text
closures_needed = ceil((target_rate * denominator) - compliant_count)
```

If closures needed is less than 0, set to 0.

---

## 11. Synthetic Data Generation Design

Generate enough data to feel real but not heavy.

Recommended v1 scale:

| Dataset | Row count |
|---|---:|
| members | 10,000 |
| claims | 35,000 |
| EHR events | 25,000 |
| screenings | 15,000 |
| outreach | 5,000 |

Synthetic data should intentionally include realistic defects:

| Defect | Rate |
|---|---:|
| Missing screening evidence | 10–20% depending measure |
| Duplicate member ID risk | 0.5–1.5% |
| Invalid / missing contact info | 8–12% |
| Positive depression screen without follow-up | 15–25% of positives |
| Screening evidence in EHR but not claims | 10–20% |
| Claims evidence without EHR event | 5–15% |
| Registry/supplemental evidence missing mapping | 3–8% |

Seed the generator for reproducibility:

```bash
python src/generate_synthetic_data.py --seed 42 --members 10000
```

---

## 12. Architecture

### Recommended stack

| Layer | Tool |
|---|---|
| Data ingestion | Python, pandas, zipfile, openpyxl |
| Synthetic generation | Python, Faker optional, numpy random seed |
| Storage | SQLite for MVP, Postgres optional later |
| Measure logic | Python + YAML definitions |
| Validation | pytest + pandera optional |
| App | Streamlit first |
| Charts | Plotly or Altair |
| Export | Markdown + CSV |
| Case study | Markdown |

### Pipeline flow

```text
CMS Star Ratings raw files
        ↓
parse_cms_star_ratings.py
        ↓
processed/cms_star_ratings_clean.csv

CDC BRFSS raw/subset files
        ↓
parse_brfss_context.py
        ↓
processed/brfss_screening_context.csv

Synthetic members / claims / EHR / screenings / outreach
        ↓
build_measure_flags.py
        ↓
measure_member_flags.csv
        ↓
calculate_measure_summary.py
        ↓
measure_summary.csv
        ↓
build_care_gap_queue.py
        ↓
care_gap_queue.csv
        ↓
build_data_quality_audit.py
        ↓
data_quality_audit.csv
        ↓
export_decision_pack.py
        ↓
outputs/decision_pack.md
```

---

## 13. Repository Structure

```text
hedis-stars-quality-control-room/
  README.md
  case_study.md
  DESIGN.md
  requirements.txt
  pyproject.toml
  .gitignore

  data/
    raw/
      cms_star_ratings/
      brfss/
    synthetic/
      members.csv
      claims.csv
      ehr_events.csv
      screenings.csv
      outreach.csv
    processed/
      cms_star_ratings_clean.csv
      brfss_screening_context.csv
      measure_member_flags.csv
      measure_summary.csv
      care_gap_queue.csv
      data_quality_audit.csv
      impact_simulation.csv

  rules/
    measure_definitions.yaml
    data_quality_rules.yaml

  src/
    __init__.py
    config.py
    generate_synthetic_data.py
    ingest_cms_star_ratings.py
    ingest_brfss_context.py
    load_rules.py
    build_measure_flags.py
    calculate_measure_summary.py
    build_care_gap_queue.py
    build_data_quality_audit.py
    impact_simulator.py
    export_decision_pack.py

  app/
    streamlit_app.py
    pages/
      1_Executive_Summary.py
      2_CMS_Stars_Benchmark.py
      3_BRFSS_Population_Context.py
      4_Measure_Performance.py
      5_Care_Gap_Queue.py
      6_Data_Completeness_Audit.py
      7_Impact_Simulator.py
      8_Decision_Pack.py

  outputs/
    decision_pack.md
    screenshots/
    tables/

  tests/
    test_measure_logic.py
    test_gap_counts.py
    test_exclusions.py
    test_data_quality_rules.py
    test_impact_simulator.py
```

---

## 14. Command-Line Interface

Implement a simple CLI pattern.

```bash
# Install
pip install -r requirements.txt

# Generate synthetic data
python src/generate_synthetic_data.py --seed 42 --members 10000

# Ingest real public data
python src/ingest_cms_star_ratings.py
python src/ingest_brfss_context.py

# Build measure outputs
python src/build_measure_flags.py
python src/calculate_measure_summary.py
python src/build_care_gap_queue.py
python src/build_data_quality_audit.py

# Export decision pack
python src/export_decision_pack.py

# Run app
streamlit run app/streamlit_app.py

# Run tests
pytest
```

---

## 15. Output Artifacts

Minimum required artifacts:

| Artifact | Path | Purpose |
|---|---|---|
| Measure summary | `data/processed/measure_summary.csv` | Shows measure rates, gaps, targets |
| Care gap queue | `data/processed/care_gap_queue.csv` | Operational outreach queue |
| Data quality audit | `data/processed/data_quality_audit.csv` | Missing evidence / source risk |
| CMS Stars clean file | `data/processed/cms_star_ratings_clean.csv` | Real benchmark layer |
| BRFSS context file | `data/processed/brfss_screening_context.csv` | Population context |
| Decision pack | `outputs/decision_pack.md` | Case-study artifact |
| Screenshots | `outputs/screenshots/` | README proof |
| Case study | `case_study.md` | Recruiter/hiring artifact |

---

## 16. Case Study Requirements

The case study should be created while building, not after.

### Required case study sections

```markdown
# HEDIS & Stars Quality Performance Control Room — Case Study

## Executive Summary
## Business Problem
## Data Sources
## Analytical Questions
## Solution Design
## Measure Logic
## Care Gap Queue
## Data Completeness Audit
## Impact Simulator
## Results
## Business Value
## Recruiter Translation
## Limitations
## Next Steps
```

### Business problem language

Use this framing:

> Health plans and provider organizations can see quality-measure performance at a reporting level, but operational teams still need to know which members have open gaps, what evidence is missing, who owns outreach, and how many closures are needed to reach target performance.

### Recruiter translation table

| Hiring need | Project evidence |
|---|---|
| HEDIS / quality reporting | Denominator, numerator, exclusions, rate, target, and gap-to-target logic |
| Population health analytics | BRFSS screening / prevention context |
| Healthcare data quality | Data completeness checks across claims, EHR, registry, and outreach sources |
| EHR data analyst work | Evidence-source validation and clinical-event logic |
| Stars / payer quality analytics | CMS Star Ratings benchmarking |
| Operational reporting | Care gap queue, outreach owner, and next-action recommendations |

---

## 17. App Visual Requirements

The final app must produce screenshots that make sense to a non-technical recruiter.

Required screenshots:

1. Executive Summary dashboard.
2. Measure Performance table.
3. Care Gap Queue.
4. Data Completeness Audit.
5. Impact Simulator.
6. Decision Pack preview.

Screenshot naming convention:

```text
outputs/screenshots/01_executive_summary.png
outputs/screenshots/02_measure_performance.png
outputs/screenshots/03_care_gap_queue.png
outputs/screenshots/04_data_completeness_audit.png
outputs/screenshots/05_impact_simulator.png
outputs/screenshots/06_decision_pack_preview.png
```

---

## 18. Data Quality Rules

Create `rules/data_quality_rules.yaml`.

Example rules:

```yaml
- rule_id: MEMBER_001
  name: Missing date of birth
  domain: member
  severity: blocker
  check_type: missing_required_field
  field: dob
  downstream_risk: Cannot evaluate age-based quality measures
  owner: Data Quality / Eligibility
  recommended_action: Verify demographics and reload eligibility file

- rule_id: SCREEN_001
  name: Screening record missing date
  domain: screening
  severity: high
  check_type: missing_required_field
  field: screening_date
  downstream_risk: Cannot count evidence in measure lookback window
  owner: EHR Data / Quality Reporting
  recommended_action: Validate screening event date from source system

- rule_id: PDS_001
  name: Positive postpartum depression screen without follow-up
  domain: behavioral_health
  severity: blocker
  check_type: missing_follow_up
  downstream_risk: Open care gap and patient follow-up risk
  owner: Care Team / Population Health
  recommended_action: Contact member and document follow-up plan
```

Outputs should include:

| Field | Description |
|---|---|
| `rule_id` | Rule identifier |
| `domain` | Member / claim / EHR / screening / outreach |
| `severity` | Blocker / High / Medium / Low |
| `failed_record_id` | Source record |
| `member_id` | If available |
| `downstream_risk` | Operational risk |
| `owner` | Responsible queue |
| `recommended_action` | Next step |

---

## 19. Testing Plan

### Unit tests

| Test file | Purpose |
|---|---|
| `test_measure_logic.py` | Confirm denominator / numerator / gap flags work |
| `test_gap_counts.py` | Confirm summary counts match member flags |
| `test_exclusions.py` | Confirm exclusions reduce denominator correctly |
| `test_data_quality_rules.py` | Confirm invalid records trigger expected defects |
| `test_impact_simulator.py` | Confirm projected rates and closures-needed calculations |

### Required tests

- A member outside age range is not eligible.
- A member with valid screening evidence is compliant.
- A member without screening evidence has an open gap.
- An excluded member is not counted in denominator.
- A positive depression screen without follow-up creates a blocker gap.
- A missing screening date triggers a high-severity data quality issue.
- Gap-to-target cannot return negative closure count.
- Closing high-priority gaps increases the projected rate.

---

## 20. Acceptance Criteria

The project is MVP-complete when:

- Synthetic data generation is reproducible with a seed.
- At least 5 measures are defined in YAML.
- Measure summary output is generated.
- Member-level care gap queue is generated.
- Data completeness audit is generated.
- CMS Star Ratings parser produces a clean benchmark file or documented curated extract.
- BRFSS parser produces a clean context file or documented curated extract.
- Streamlit app has all MVP views.
- Decision pack export works.
- Case study exists and includes results.
- Tests pass.
- README explains public-safe design and includes screenshots.

---

## 21. Build Phases for Coding Agent

### Phase 1 — Scaffold

Agent task:

```text
Create the repository scaffold for HEDIS & Stars Quality Performance Control Room. Add folders, requirements, empty modules, README stub, DESIGN.md, case_study.md, and test placeholders. Do not build app logic yet.
```

### Phase 2 — Synthetic data

Agent task:

```text
Implement reproducible synthetic data generation for members, claims, EHR events, screenings, and outreach. Use seed 42. Generate 10,000 members and realistic event tables. Inject documented data quality defects. Save outputs to data/synthetic/.
```

### Phase 3 — Measure definitions

Agent task:

```text
Create rules/measure_definitions.yaml for BCS_SIM, CCS_SIM, COL_SIM, PND_SIM, and PDS_SIM. Implement a rule loader and measure flag builder that outputs member-level eligibility, exclusion, compliance, and gap flags.
```

### Phase 4 — Measure summary + care gap queue

Agent task:

```text
Build measure_summary.csv and care_gap_queue.csv. Include denominator, numerator, exclusions, open gaps, rate, target, gap-to-target, priority, owner, evidence_missing, and recommended_action.
```

### Phase 5 — Data completeness audit

Agent task:

```text
Implement data quality rules and output data_quality_audit.csv. Include missing evidence, duplicate IDs, invalid dates, orphan records, positive depression screens without follow-up, and measure-level missing evidence risk.
```

### Phase 6 — Real data ingestion

Agent task:

```text
Add ingestion scripts for CMS Star Ratings and BRFSS context. If full raw ingestion is too heavy, create documented curated extracts and clearly preserve source URLs and transformation notes.
```

### Phase 7 — Streamlit app

Agent task:

```text
Build a Streamlit app with Executive Summary, CMS Stars Benchmark, BRFSS Population Context, Measure Performance, Care Gap Queue, Data Completeness Audit, Impact Simulator, and Decision Pack views.
```

### Phase 8 — Decision pack + case study

Agent task:

```text
Implement export_decision_pack.py and write case_study.md using actual generated outputs. Include recruiter translation, limitations, screenshots, and public-safe disclaimer.
```

---

## 22. README Requirements

README should open with:

```markdown
# HEDIS & Stars Quality Performance Control Room

A public-safe healthcare quality analytics project that combines real CMS Star Ratings benchmarking, public BRFSS population-health context, and synthetic member-level care-gap operations.

The system identifies underperforming quality measures, open care gaps, missing evidence sources, outreach priorities, and projected gap closures needed to reach target performance.
```

README must include:

- Screenshot of executive summary.
- Case study link.
- Project architecture diagram or text pipeline.
- Data source table.
- Public-safe disclaimer.
- How to run.
- Outputs generated.
- Recruiter translation.

---

## 23. Portfolio Positioning

Once complete, update the main data portfolio:

### Add to Healthcare Data Quality / EHR Workflow packet

Lead with this project:

> **HEDIS & Stars Quality Performance Control Room** — real CMS Star Ratings benchmarking + public BRFSS context + synthetic member-level care-gap operations.

Move Lab SLA & QC Analytics to supporting proof.

### Add to README project tracks

Under `Healthcare Data Quality / EHR Workflow`:

| Project | Best evidence |
|---|---|
| HEDIS & Stars Quality Performance Control Room | CMS Stars benchmark, BRFSS context, HEDIS-inspired care gap queue, data completeness audit, impact simulator |
| Healthcare Encounters QA Evidence Pack | Reject severity, pre-submission data quality |
| Lab SLA & QC Analytics | Clinical workflow literacy, SLA/TAT/QC operational analysis |

---

## 24. Final Success Standard

This project should make a recruiter think:

> This candidate understands healthcare quality analytics, HEDIS/Stars language, care gaps, EHR/claims evidence, data completeness, and operational reporting. He is not just building charts; he is building a decision workflow.

The project is successful if it supports applications for:

- HEDIS Data Analyst
- Population Health Data Analyst
- Quality Improvement Data Analyst
- Stars Analyst
- Healthcare Data Quality Analyst
- EHR Data Analyst
- Health IT Data Analyst
- Healthcare BI Analyst
- Provider Performance Analyst

---

## 25. Source Links

- CMS Part C and D Performance Data: https://www.cms.gov/medicare/health-drug-plans/part-c-d-performance-data
- CDC BRFSS Annual Survey Data: https://www.cdc.gov/brfss/annual_data/annual_data.htm
- NCQA HEDIS ECDS Reporting: https://www.ncqa.org/resources/hedis-electronic-clinical-data-systems-ecds-reporting/

---

## 26. Working Principle

Do not build this as “another dashboard.”

Build it as a quality operations system:

```text
Real benchmark context
+ Public population context
+ Synthetic member-level operations
+ Transparent measure logic
+ Data completeness checks
+ Outreach prioritization
+ Impact simulation
+ Decision pack
= Hireable healthcare quality analytics case study
```
