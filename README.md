# Churn Lens: Telecom Retention Intelligence

An interactive portfolio presentation of a telecom customer churn analysis and Random Forest classification project.

## Open the project

Open `index.html` in a browser. The dashboard works without a build step or backend. `techno_churn.html` contains the detailed Jupyter analysis and model evaluation.

## Highlights

- 7,043 source records, cleaned to 7,021 after duplicate removal
- 26.6% churn rate in the original 7,043-row cohort
- Random Forest test accuracy: 80%
- Churn-class recall: 53%
- Feature importance analysis across 19 encoded predictors

## Privacy

The repository contains an anonymized CSV for reproducibility. It intentionally excludes customer IDs, the raw workbook, serialized model files, and the notebook export. The dashboard uses aggregate results from the analysis.

## Stack

Python, pandas, seaborn, scikit-learn, Random Forest, HTML, CSS, JavaScript