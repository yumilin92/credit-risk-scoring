# 💳 Credit Risk Scoring — Explainable AI for Loan Default Prediction

## Overview

A production-ready credit risk model that predicts loan default probability
and explains individual decisions using SHAP — meeting regulatory requirements
of Japan's FSA and EU AI Act.

## Business Problem

Banks must assess borrower default risk AND explain rejection reasons.
Black-box models are not acceptable under modern financial regulations.
This project solves both: high predictive accuracy + full explainability.

## Results

| Metric | Logistic Regression | XGBoost | LightGBM |
|--------|-------------------|---------|----------|
| ROC-AUC | 0.8612 | 0.9508 | **0.9515** |
| Gini | 0.7223 | 0.9015 | **0.9031** |
| KS Statistic | 0.5698 | 0.7688 | **0.7678** |
| Expected Loss Accuracy | 27.9% | 74.2% | **89.3%** |

**LightGBM predicted expected losses within 10.7% of actual losses.**

## Key Features

- **Explainable AI** — SHAP waterfall plots for every loan decision
- **Financial metrics** — Gini coefficient, KS statistic, Expected Loss (Basel III)
- **Regulatory compliance** — individual rejection explanations
- **Data quality** — outlier removal, missing value imputation
- **Feature engineering** — debt-to-income ratio, risk tiers

## Dataset

[Credit Risk Dataset](https://www.kaggle.com/datasets/laotse/credit-risk-dataset)
— 32,581 borrowers, 12 features, 21.8% default rate

## Tech Stack

Python · LightGBM · XGBoost · Scikit-learn · SHAP · Pandas · Matplotlib

## Project Structure
```
credit-risk-scoring/
├── data/
│   └── credit_risk_dataset.csv
├── visuals/
│   ├── eda.png
│   ├── shap_summary.png
│   └── shap_waterfall.png
└── 01_eda_baseline.ipynb
```

## Sample Decision Explanation
```
Applicant: Age 49, Income 15,000 USD, Loan 2,400 USD
Decision: REJECTED (98.6% default probability)

Top reasons:
🔴 person_income = 15,000 USD  (+6.45) — insufficient income
🔴 person_home_ownership = RENT (+0.29) — renter, higher risk
🟢 loan_grade = A              (-0.37) — good credit grade
🟢 person_age = 49             (-0.44) — older, more stable
```

## Author

Yulia Vovk — Data Scientist | Tokyo
[GitHub](https://github.com/yumilin92)
