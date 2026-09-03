# Churn Lens: Telecom Retention Intelligence

> An interactive customer churn case study that turns telecom behavior, billing, and contract signals into retention priorities.

[Explore the interactive dashboard](index.html) · [Download the anonymized dataset](churn_dataset_anonymized.csv)

## Why this project matters

Customer churn is not only a classification problem. A useful retention model should help a team decide **who to contact, why they may be at risk, and what to do next**. This project combines exploratory data analysis with a Random Forest classifier and presents the findings in a recruiter-friendly interactive dashboard.

## Key results

| Measure | Result |
| --- | ---: |
| Original customer records | 7,043 |
| Modeling records after duplicate removal | 7,021 |
| Original-cohort churn rate | 26.6% |
| Held-out test records | 1,405 |
| Test accuracy | 80% |
| Churn-class recall | 53% |

The model recognizes retained customers more reliably than churned customers, which is an important operational limitation: a retention team should review the decision threshold and optimize for recall before using the model for outreach.

## What the dashboard shows

- **Overview:** cohort scale, churn mix, and model scorecard
- **Churn drivers:** Random Forest feature importance and business interpretation
- **Risk simulator:** transparent, illustrative profile exploration for early-tenure and support scenarios

## Top model signals

The strongest feature-importance signals were `TotalCharges`, `MonthlyCharges`, `tenure`, `Contract`, and `PaymentMethod`. Feature importance indicates contribution to model decisions, not causation.

## Workflow and tools

1. Loaded and profiled the telecom customer dataset.
2. Removed customer identifiers and duplicate rows.
3. Converted `TotalCharges` to numeric and handled missing values.
4. Encoded categorical variables and scaled model inputs.
5. Trained and evaluated a Random Forest classifier.
6. Reviewed accuracy, classification metrics, confusion matrix, ROC curve, and feature importance.
7. Translated aggregate findings into an HTML/CSS/JavaScript dashboard.

**Tools:** Python, pandas, NumPy, seaborn, scikit-learn, Random Forest, HTML, CSS, JavaScript

## Run locally

Open `index.html` directly in a browser. No build step, package install, or backend is required.

## Privacy and data note

The published CSV is anonymized and excludes `customerID`. The raw Excel workbook, serialized model, and notebook export are intentionally excluded. The dashboard's risk simulator is illustrative and is not a live prediction API.

## Repository structure

```text
index.html                    Interactive portfolio dashboard
churn_dataset_anonymized.csv  Privacy-safe dataset for reproducibility
README.md                     Project documentation
.gitignore                    Rules for raw data and model artifacts
```