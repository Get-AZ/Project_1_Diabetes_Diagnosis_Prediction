# Diabetes Diagnosis Prediction — Portfolio Project

## Project Summary

I developed a reproducible binary-classification workflow for predicting diabetes
outcomes using Logistic Regression.

The project covers data quality, exploratory analysis, preprocessing, model comparison,
evaluation, explainability, threshold analysis, artifact integrity, and reproducibility.

## Key Result

The final champion was **Baseline Logistic Regression**.

- **Accuracy:** 0.7143
- **Precision:** 0.6087
- **Recall:** 0.5185
- **F1:** 0.5600
- **ROC-AUC:** 0.8230

## Technical Highlights

- Python
- pandas
- NumPy
- scikit-learn
- Logistic Regression
- StandardScaler
- SimpleImputer
- Model evaluation
- Explainability
- Threshold analysis
- Model serialization
- Independent reproducibility validation
- SHA256 integrity verification

## Engineering Focus

The project goes beyond model fitting by maintaining a reproducible evidence chain
from the original dataset through the final model artifact.

The model and dataset were independently hash-validated.

Dataset SHA256: `698c203a14aa31941d2251175330c9199f3ccdb31597abbba2a3e35416257a72`

Model SHA256: `5db1b088d1bfb18c74c9e7622e013c4258759f9f6f9e34a6a4d4398f8febba9c`

## Responsible AI

This is an academic and portfolio project, not a clinically validated diagnostic system.

The model should not be used to make medical decisions.

External validation, prospective validation, calibration, clinical utility analysis,
and formal clinical governance were outside the project's scope.

## Portfolio Takeaway

This project demonstrates the ability to move beyond simply fitting a model and build
a reproducible, explainable, integrity-validated machine-learning workflow.