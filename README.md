# Telecom Customer Churn Analysis and Prediction

> A Python data science project using exploratory data analysis and classification models to understand telecom customer churn and support retention decisions.

[Open the interactive dashboard](index.html) · [Download the anonymized CSV](churn_dataset_anonymized.csv)

## Project Overview

This project analyzes a telecom customer dataset and builds a supervised machine learning workflow for churn classification. The public dashboard presents aggregate findings, feature importance, model metrics, and an illustrative risk simulator without exposing customer identifiers.

## Problem Statement

Telecom providers need to identify customers who may churn so retention teams can prioritize proactive outreach. The project examines customer tenure, charges, contract details, payment method, internet service, and support services as signals associated with the churn outcome.

## Objectives

- Understand the structure and quality of the customer dataset.
- Explore churn distribution and relationships between customer attributes and churn.
- Prepare categorical and numerical features for machine learning.
- Train and compare classification models.
- Evaluate performance using accuracy, precision, recall, F1-score, confusion matrix, and ROC visualization.
- Communicate findings through an interactive, privacy-safe dashboard.

## Key Features

- Interactive overview with cohort metrics and model scorecard.
- Churn-driver view based on Random Forest feature importance.
- Illustrative risk simulator for contract, support, and tenure scenarios.
- Anonymized CSV for reproducibility.
- No backend or build step required for the dashboard.

## Dataset Information

The dataset contains 7,043 telecom customer records and 21 original columns, including customer attributes, services, billing fields, and the `Churn` target. The public CSV removes `customerID` and retains 20 analytical columns. The modeling workflow reports 7,021 rows after duplicate removal and uses an 80/20 stratified train-test split, producing 1,405 held-out records.

## Technologies and Tools

- **Programming:** Python
- **Data science:** pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Machine learning:** scikit-learn, Random Forest, Logistic Regression, Decision Tree, optional XGBoost
- **Model utilities:** joblib, StandardScaler, LabelEncoder, train-test split
- **Data input:** Excel and CSV
- **Web presentation:** HTML, CSS, JavaScript

SQL, MySQL, PostgreSQL, Power BI, and Generative AI are not used in this repository and are intentionally not listed as project technologies.

## Data Cleaning

- Removed the customer identifier from the modeling features.
- Converted `TotalCharges` from text to numeric values.
- Replaced invalid or blank charge values with missing values and filled them with the median in the analysis workflow.
- Checked missing values and duplicate rows.
- Removed 22 duplicate rows before modeling.

## Exploratory Data Analysis

The analysis investigates churn distribution, gender, contract type, payment method, internet service, monthly charges, total charges, tenure, outliers, and feature correlation. The strongest business signals in the Random Forest feature-importance output are `TotalCharges`, `MonthlyCharges`, `tenure`, `Contract`, and `PaymentMethod`.

## Feature Engineering

- Encoded categorical columns with `LabelEncoder`.
- Separated predictors from the `Churn` target.
- Applied `StandardScaler` after the stratified split.
- Used 19 encoded predictors in the model input.

## Machine Learning Models

The notebook experiments with Logistic Regression, Decision Tree, Random Forest, and optional XGBoost. The reported classification metrics and feature-importance analysis correspond to the Random Forest workflow, initialized with `random_state=42`.

## Model Evaluation

| Metric | Reported result |
| --- | ---: |
| Accuracy | 0.80 |
| Retained-class precision | 0.84 |
| Retained-class recall | 0.90 |
| Retained-class F1-score | 0.87 |
| Churn-class precision | 0.65 |
| Churn-class recall | 0.53 |
| Churn-class F1-score | 0.58 |
| Evaluation set | 1,405 records |

The model identifies retained customers more reliably than churned customers. That recall gap is a meaningful limitation: a production retention workflow would need threshold tuning, class-imbalance analysis, and business-cost evaluation before deployment.

## Important Findings and Results

- The original cohort churn rate is 26.6%: 1,869 churned and 5,174 retained customers.
- Billing-related variables and tenure are the largest feature-importance signals in the reported Random Forest output.
- Contract and payment method provide additional behavioral context for prioritizing outreach.
- The result is a student portfolio analysis, not a production scoring service or causal study.

## Visualizations

The dashboard includes a churn mix, model scorecard, feature-importance bars, and an illustrative risk simulator. The original notebook export is not published because its rendered sample tables contain customer identifiers.

## Installation

For the Python analysis workflow, use Python 3.10+ and install the dependencies:

```bash
python -m pip install -r requirements.txt
```

## How to Run

Open `index.html` directly in a browser to view the interactive dashboard. No server, package install, or backend is required for the dashboard.

The original analysis was developed in a Jupyter workflow using the local Excel source file. That raw workbook and notebook export are intentionally not part of the public repository.

## Example Usage

1. Open the dashboard.
2. Review the overview metrics and model scorecard.
3. Select **Churn drivers** to inspect the model's main signals.
4. Select **Risk simulator** and change contract, support, or tenure to explore the illustrative risk logic.
5. Download the anonymized CSV for independent analysis.

## Skills Demonstrated

Python programming, data cleaning, exploratory data analysis, data visualization, categorical encoding, feature scaling, supervised machine learning, classification evaluation, feature importance interpretation, privacy-aware data sharing, and dashboard communication.

## Future Improvements

- Add a reproducible notebook or Python training script using only the anonymized CSV.
- Compare models with cross-validation and record each model's metrics.
- Tune the classification threshold for higher churn recall.
- Add precision-recall and calibration analysis.
- Replace label encoding with a documented preprocessing pipeline where appropriate.
- Add automated tests and continuous integration.

## Project Structure

```text
index.html                    Interactive portfolio dashboard
churn_dataset_anonymized.csv  Privacy-safe dataset for reproducibility
requirements.txt              Python dependencies used by the analysis
README.md                     Project documentation
.gitignore                    Rules for raw data and model artifacts
```

## Recruiter Keywords

**Programming:** Python

**Data Science:** pandas, NumPy, exploratory data analysis, feature engineering, data cleaning, predictive modeling

**Data Analytics:** customer churn analysis, retention analytics, cohort analysis, business insights

**Machine Learning:** scikit-learn, classification, Logistic Regression, Decision Tree, Random Forest, XGBoost, feature importance, model evaluation

**Databases:** No database technology is used in this project.

**Visualization:** Matplotlib, Seaborn, data visualization, confusion matrix, ROC curve

**Tools:** Jupyter, Excel input, HTML, CSS, JavaScript, joblib

## Resume Connection

- Analyzed 7,043 telecom customer records with Python, pandas, NumPy, Matplotlib, and Seaborn; cleaned duplicate and billing fields and translated churn patterns into retention insights.
- Trained and evaluated a Random Forest classifier with scikit-learn on 1,405 held-out records, achieving 80% accuracy and 53% recall for the churn class.
- Built an interactive HTML/CSS/JavaScript dashboard presenting churn drivers, model evaluation, and privacy-safe customer-risk exploration without publishing customer IDs.

## Author

**Bhupesh Kumar**
BCA in Data Science · Aspiring Data Scientist / Data Analyst

## Contact

- GitHub: [Bhupesh-datascie](https://github.com/Bhupesh-datascie)
- LinkedIn: `https://www.linkedin.com/in/your-profile`
- Email: `bhupeshram383@gmail.com`

## Privacy Note

The published CSV excludes `customerID`. Raw Excel data, serialized models, and the notebook export are excluded to avoid publishing customer-level identifiers. The dashboard risk simulator is illustrative and is not a live prediction API.