# UzExperiment — Product A/B Testing & Decision Intelligence

An end-to-end A/B testing project demonstrating product experimentation,
statistical inference, revenue analysis, CUPED variance reduction,
guardrail monitoring, segmentation, and reproducible reporting.

---

## Business Problem

A hypothetical Uzbekistan-based digital commerce company is testing a
redesigned checkout experience.

The experiment asks:

> Does the redesigned checkout increase conversion and revenue without
> deteriorating payment success?

---

## Important Data Disclosure

**The user-level experiment dataset is SYNTHETIC.**

It was generated specifically for this portfolio project and does not
represent customers or experimental results from a real company.

Real public Uzbekistan data was used for market context and data engineering.

---

## Experiment Design

| Component | Definition |
|---|---|
| Experiment | Checkout redesign |
| Control | A |
| Treatment | B |
| Users | 50,000 |
| Primary metric | Conversion rate |
| Business metric | Revenue per user |
| Variance reduction | CUPED |
| Guardrail | Payment success rate |
| Random seed | 42 |

---

## Results

| Metric | Control | Treatment | Change |
|---|---:|---:|---:|
| Conversion | 10.78% | 12.30% | +1.52 pp |
| Revenue / user | 37,315 UZS | 41,924 UZS | +4,609 UZS |
| CUPED RPU | 37,068 UZS | 42,169 UZS | +5,101 UZS |
| Payment success | 93.14% | 93.43% | +0.28 pp |

### Conversion inference

95% confidence interval for the treatment-control conversion difference:

**[0.96%, 2.08%]**

### Revenue inference

Bootstrap 95% confidence interval for the RPU difference:

**[1,900, 7,265] UZS**

### CUPED

Revenue variance reduction:

**4.56%**

---

## Experiment Health

| Check | Result |
|---|---|
| Sample Ratio Mismatch | PASS |
| Duplicate user IDs | PASS |
| Missing variants | PASS |
| Invalid conversion values | PASS |
| Negative order values | PASS |
| Missing payment outcomes | PASS |
| Conversion CI excludes zero | PASS |
| Revenue bootstrap CI excludes zero | PASS |
| Payment guardrail deterioration | PASS |

SRM p-value: **0.3296**

---

## Statistical Methods

- Randomized A/B assignment
- Conversion-rate inference
- Two-sided hypothesis testing
- Welch's t-test
- Bootstrap confidence intervals
- CUPED variance reduction
- Logistic regression
- Treatment × segment interaction analysis
- Benjamini-Hochberg FDR correction
- Sample Ratio Mismatch testing
- Data-quality validation
- Minimum detectable effect analysis

---

## Segment Analysis

Observed conversion lifts:

- Desktop: **+0.69 pp**
- Mobile: **+1.66 pp**
- Tablet: **+3.81 pp**

These are descriptive estimates.

After multiple-testing correction, the segment interaction evidence did
not remain statistically significant. Therefore, the observed differences
should not be treated as confirmed heterogeneous treatment effects.

---

## Power & MDE

With approximately 25,000 users per group, the experiment was designed
to detect approximately:

- **0.79 percentage points absolute lift**
- **7.32% relative lift**

at approximately 80% statistical power and a 5% significance level.

---

## Portfolio Skills Demonstrated

**Product Analytics**
- KPI definition
- Experiment design
- Conversion analysis
- Revenue analysis
- Guardrail metrics

**Statistics**
- Confidence intervals
- Hypothesis testing
- Bootstrap inference
- Power analysis
- MDE
- Multiple-testing correction

**Advanced Experimentation**
- CUPED
- Segment interaction analysis
- Sample Ratio Mismatch detection

**Data Engineering**
- Public-data ingestion
- Raw/processed data separation
- Data cleaning
- Data-quality validation
- Reproducible file structure

**Visualization & Reporting**
- KPI dashboard
- Segment visualization
- Executive summary
- Reproducible case-study report

---

## Project Structure

```text
UzExperiment/
├── README.md
├── data/
│   ├── raw/
│   │   └── cbu_payment_2025.xls
│   └── processed/
│       ├── cbu_payment_2025_clean.csv
│       ├── cbu_market_baseline.csv
│       ├── experiment_final_results.csv
│       └── synthetic_experiment_users.csv
└── reports/
    ├── device_conversion_lift.png
    ├── experiment_health_summary.csv
    ├── executive_experiment_summary.csv
    ├── experiment_kpi_dashboard.png
    └── UzExperiment_case_study.md
```

---

## Reproducibility

The project was developed entirely in Google Colab.

Random seed: **42**

A fixed random seed allows the synthetic experiment to be regenerated
consistently.

---

## Project Status

**Complete — portfolio-ready analytical case study.**