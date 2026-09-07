# Bank Marketing Response Modelling and Customer Propensity Analysis

A collaborative statistical and machine learning study of bank marketing response. The notebooks explore customer characteristics, campaign history and economic context, then compare classifiers for the recorded subscription outcome. The current experiments include call duration, making them retrospective response models rather than validated tools for choosing customers before a call.

## The question

Which recorded customer and campaign characteristics are associated with subscription response, and how do classification methods trade precision against recall?

## Tools and methods

Python, pandas, scikit learn, XGBoost, Classification, Exploratory analysis, Model evaluation.

## Work in this repository

1. Profiled 41,188 records with 21 source columns and explored demographic, contact, campaign and economic variables.
2. Prepared encoded and scaled datasets and investigated response imbalance.
3. Compared Logistic Regression, Random Forest and XGBoost, including tuned model variants.
4. Produced confusion matrices, ROC comparisons and feature importance charts to examine model behaviour.
5. Documented in exploratory analysis that call duration is unavailable before contact and can compromise a prospective targeting claim.

## Evidence and scope

| Measure | Recorded value |
| --- | --- |
| Source records | 41,188 |
| Source columns | 21 |
| Recorded test partition in the modelling notebook | 8,238 records |
| Classifier families compared | Logistic Regression, Random Forest and XGBoost |

## Repository guide

| File or folder | Purpose |
| --- | --- |
| [notebook/Stats_project.ipynb](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/notebook/Stats_project.ipynb) | Preparation, modelling and saved evaluation outputs |
| [notebook/bank_marketing.ipynb](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/notebook/bank_marketing.ipynb) | Exploration and duration limitation |
| [data/raw/bank-additional-full.csv](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/data/raw/bank-additional-full.csv) | Source table |
| [data/cleaned/bank_marketing_cleaned_unscaled.csv](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/data/cleaned/bank_marketing_cleaned_unscaled.csv) | Prepared data |
| [graphs/roc_comparison_tunedRF_XGB.png](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/graphs/roc_comparison_tunedRF_XGB.png) | Recorded ROC comparison |
| [graphs/Tuned_Random_Forest_confusion.png](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/graphs/Tuned_Random_Forest_confusion.png) | Random Forest confusion matrix |
| [graphs/xgb_top30_feature_importance.png](https://github.com/divyansh2703/Propensity_Model_Bank_Coustomer/blob/main/graphs/xgb_top30_feature_importance.png) | XGBoost feature importance |

## Getting started

Open `notebook/Stats_project.ipynb` and `notebook/bank_marketing.ipynb` in Jupyter or VS Code. The notebooks use files by short names, so update their input and output paths to the committed `data/raw/` and `data/cleaned/` locations. Review imports and prepare a dedicated Python environment with pandas, NumPy, Matplotlib, seaborn, scikit learn and XGBoost.

For faithful review of the historical work, inspect the saved notebook outputs. For a prospective model, define the scoring time first, exclude information unavailable then and fit preprocessing within the training folds. No fresh training or claim of production readiness is included in this documentation update.

## Current limitations

1. Call duration is present in the current modelling workflow. Historical scores cannot be advertised as validated performance for selecting customers before a call.
2. The preparation workflow performs transformations before the final modelling split. A revised evaluation should fit learned preprocessing exclusively on training data.
3. Repeated comparison on a test partition can turn it into a selection set. A new untouched holdout is needed for a final performance claim.
4. No campaign conversion lift, customer acquisition saving or deployed bank usage is established by the repository.

## Next steps

1. Rebuild a precontact model without call duration or other unavailable fields.
2. Move learned preprocessing inside training folds.
3. Evaluate on an untouched holdout and report response capture at a defined contact capacity.

## Authors and reuse

Divyansh Doshi, Vaibhav Vijay Dhudas and Geebhabalan Devaraj Sumithra.

Documentation reviewed against the public repository on 7 September 2026. Counts are taken from the named saved artifacts or directly inspected CSVs; this review did not rerun model training or validate a complete deployment. No source code licence was found in the reviewed project tree. Data and third party material may have separate terms.
