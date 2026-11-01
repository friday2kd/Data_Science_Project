# Customer Churn Prediction

A bias-aware churn analysis on the public IBM Telco Customer Churn dataset (7,043 customers). The notebook covers data checks, EDA, leakage-safe preprocessing, cross-validated model selection, holdout evaluation, permutation importance, calibration, a subgroup error audit and outreach threshold selection.

## Key results

| | Value |
|---|---|
| Selected model | Logistic Regression (by 5-fold CV PR-AUC) |
| CV ROC-AUC / PR-AUC | 0.846 / 0.661 |
| Holdout ROC-AUC / PR-AUC | 0.842 / 0.633 |
| Top 20% by risk | captures ~50% of churners |
| Threshold 0.35 (holdout) | recall 70.6%, F1 61.5% |

Tenure, internet service type, monthly charges and contract type are the strongest predictors. These are associations, not causes.

## Files

- `customer_churn_analysis.ipynb`: the analysis, with outputs
- `customer_churn_analysis.html`: rendered copy for quick viewing

## Run it

1. Download `Telco-Customer-Churn.csv` from [IBM's sample repo](https://github.com/IBM/telco-customer-churn-on-icp4d/tree/master/data) (Apache 2.0) and save it as `data/telco_customer_churn.csv`.
2. `pip install -r requirements.txt`
3. Open the notebook and run all cells.

The data file is not committed to this repo.

## Limitations

Random train/test split (no out-of-time validation), observational data only, and subgroup results reported without confidence intervals. See Stage 9 in the notebook.
