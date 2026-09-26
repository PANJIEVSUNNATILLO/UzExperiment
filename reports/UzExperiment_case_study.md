# UzExperiment — Product A/B Testing & Decision Intelligence

## 1. Project Overview

UzExperiment is a portfolio-grade experimentation project designed around
a checkout redesign for a hypothetical Uzbekistan-based digital commerce
business.

The project demonstrates an end-to-end A/B testing workflow:

- experiment design
- randomized treatment assignment
- conversion analysis
- revenue analysis
- bootstrap inference
- CUPED variance reduction
- guardrail monitoring
- segment analysis
- multiple-testing correction
- sample-ratio mismatch detection
- data-quality validation
- reproducible reporting

## 2. Data Provenance

### Real public data

Public Uzbekistan payment-system data from the Central Bank of Uzbekistan
was used to establish market context and demonstrate real-world data
ingestion and cleaning.

### Synthetic experiment data

All user-level experiment observations are SYNTHETIC.

They were generated specifically for this portfolio project and do not
represent customers or experimental results from a real Uzbek company.

## 3. Experiment Design

Experiment:
Checkout redesign

Variants:
- Control (A)
- Treatment (B)

Users:
50,000

Approximate allocation:
- Control: 24,891
- Treatment: 25,109

Primary metric:
Conversion rate

Business metric:
Revenue per user (RPU)

Variance-reduction method:
CUPED

Guardrail:
Payment success rate

## 4. Primary Metric

Control conversion:
10.78%

Treatment conversion:
12.30%

Absolute lift:
+1.52%

95% confidence interval:
[0.96%, 2.08%]

The confidence interval for the treatment-control difference is entirely
above zero.

## 5. Revenue Analysis

Control RPU:
37,315.21 UZS

Treatment RPU:
41,924.23 UZS

Raw RPU difference:
4,609.02 UZS

Raw relative change:
12.35%

### Bootstrap inference

95% bootstrap confidence interval:

[1,900.06, 7,265.01] UZS

The bootstrap interval is entirely above zero.

## 6. CUPED

Pre-experiment revenue was used as a predictive covariate.

Correlation with experiment-period revenue:
0.2134

Estimated CUPED coefficient:
0.181189

Revenue variance reduction:
4.56%

Raw RPU difference:
4,609.02 UZS

CUPED-adjusted RPU difference:
5,100.57 UZS

CUPED demonstrates how pre-experiment information can reduce variance
and improve the precision of an experiment analysis.

## 7. Payment Guardrail

Control payment success:
93.14%

Treatment payment success:
93.43%

Absolute change:
+0.28%

The observed treatment result does not show deterioration in this
guardrail metric.

## 8. Segment Analysis

Observed conversion lift by device:

- Desktop: +0.69 percentage points
- Mobile: +1.66 percentage points
- Tablet: +3.81 percentage points

These are descriptive segment estimates.

The device interaction did not remain statistically significant after
false-discovery-rate correction.

Therefore, the segment differences should not be interpreted as
confirmed heterogeneous treatment effects.

## 9. Experiment Health

Sample Ratio Mismatch:
PASS

SRM p-value:
0.3296

Duplicate user IDs:
0

Missing variants:
0

Invalid conversion values:
0

Negative order values:
0

Missing payment outcomes among converters:
0

Conversion confidence interval excludes zero:
PASS

Revenue bootstrap confidence interval excludes zero:
PASS

Payment guardrail deterioration:
PASS

## 10. Statistical Methods

The project uses:

- two-proportion inference for conversion
- two-sided hypothesis testing
- Welch's t-test for user-level revenue
- bootstrap confidence intervals
- CUPED variance reduction
- logistic regression for treatment/segment interactions
- Benjamini-Hochberg FDR correction
- chi-square SRM testing

## 11. Key Findings

The synthetic experiment produced the following observed differences:

| Metric | Control | Treatment | Change |
|---|---:|---:|---:|
| Conversion | 10.78% | 12.30% | +1.52% |
| Revenue / user | 37,315 UZS | 41,924 UZS | +4,609 UZS |
| CUPED RPU | 37,068 UZS | 42,169 UZS | +5,101 UZS |
| Payment success | 93.14% | 93.43% | +0.28% |

## 12. Limitations

This project is intentionally synthetic at the user-experiment level.

Important limitations include:

1. The experiment does not represent a real company's customer population.
2. Treatment effects were simulated rather than observed from production.
3. Revenue is highly skewed, so revenue inference requires careful interpretation.
4. Segment analysis is exploratory and subject to multiple-testing risk.
5. CUPED effectiveness depends on the predictive strength of the
   pre-experiment covariate.
6. Real production experimentation would require monitoring additional
   metrics such as refunds, retention, latency, cancellations, and
   long-term customer value.

## 13. Reproducibility

Random seed:
42

Project structure:

UzExperiment/
- data/raw/
- data/processed/
- reports/

Key processed datasets:

- cbu_payment_2025_clean.csv
- cbu_market_baseline.csv
- synthetic_experiment_users.csv
- experiment_final_results.csv

Key report artifacts:

- device_conversion_lift.png
- experiment_health_summary.csv
- executive_experiment_summary.csv
- experiment_kpi_dashboard.png

## 14. Portfolio Takeaway

This project demonstrates an experimentation workflow that goes beyond
calculating a simple A/B conversion difference.

It combines experimental design, statistical inference, business metrics,
variance reduction, guardrails, segmentation, multiple-testing control,
data-quality validation, and reproducible reporting in a single
end-to-end analysis.