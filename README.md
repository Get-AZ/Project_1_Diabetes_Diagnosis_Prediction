# Project 1 — Diabetes Diagnosis Prediction

A reproducible binary-classification project using Logistic Regression to predict
the `Outcome` target in a diabetes dataset.

> **Important:** This is an academic and portfolio machine-learning project.
> It is **not a clinically validated diagnostic system** and must not be used
> for medical decision-making.

---

## Project Overview

This project demonstrates an end-to-end classical machine-learning workflow:

- Dataset quality assessment
- Clinical exploratory data analysis
- Train/test splitting
- Baseline vs clinical preprocessing comparison
- Logistic Regression modeling
- Holdout evaluation
- Model explainability
- Probability-threshold analysis
- Model artifact creation
- Independent reproducibility validation
- SHA256 artifact integrity validation
- Professional project packaging

## Problem Definition

**Task:** Binary classification

**Target:** `Outcome`

The model predicts the binary outcome contained in the dataset.

The objective is to demonstrate a transparent and reproducible ML workflow rather
than to create a clinically deployable diagnostic system.

## Dataset

- Observations: **768**
- Columns: **9**
- Predictive features: **8**
- Target: `Outcome`
- Outcome 0: **500**
- Outcome 1: **268**

Features:

Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age

Dataset SHA256:

`698c203a14aa31941d2251175330c9199f3ccdb31597abbba2a3e35416257a72`

## Data Quality

No pandas-detected missing values were present in the original dataset and no
duplicate rows were identified.

Several physiological variables contain zero values that are clinically suspicious:

- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI

Pregnancies was treated differently because zero pregnancies can be a legitimate value.

## Modeling Strategy

Two approaches were evaluated.

### Baseline Pipeline

StandardScaler followed by LogisticRegression.

### Clinical Preprocessing Pipeline

Suspicious zero values were converted to missing values, followed by median imputation,
StandardScaler, and LogisticRegression.

Both approaches were fitted using training data only.

## Train/Test Strategy

- Training observations: **614**
- Test observations: **154**
- Test proportion: **20%**
- Random state: **42**
- Stratification: **Yes**

## Champion Model

The **Baseline Logistic Regression** pipeline was selected as the champion.

Selection priority:

1. ROC-AUC
2. Recall
3. F1
4. Accuracy

## Holdout Results

| Metric | Score |
|---|---:|
| Accuracy | **0.7143** |
| Precision | **0.6087** |
| Recall | **0.5185** |
| F1 | **0.5600** |
| ROC-AUC | **0.8230** |

These results describe performance on the held-out academic test set and should
not be interpreted as evidence of clinical effectiveness.

## Explainability

The champion Logistic Regression model provides interpretable standardized coefficients.

Glucose had the strongest positive model association, followed by BMI and Pregnancies.

These are statistical associations within the fitted model, not causal medical conclusions.

## Threshold Analysis

Probability thresholds from 0.20 through 0.80 were evaluated.

Within the evaluated grid, threshold **0.25** produced the highest observed recall
and F1.

No clinical operating threshold was selected. Clinical threshold selection requires
intended-use definition, error-cost analysis, calibration, and appropriate validation.

## Final Model Artifact

`artifacts/diabetes_baseline_logistic_regression.joblib`

Model SHA256:

`5db1b088d1bfb18c74c9e7622e013c4258759f9f6f9e34a6a4d4398f8febba9c`

Model integrity: **PASS**

## Reproducibility

The saved model was independently loaded and validated.

Validation confirmed:

- Model loads successfully
- Model SHA256 matches recorded evidence
- Dataset SHA256 matches recorded evidence
- Pipeline structure is valid
- Eight expected features are present
- Predictions are produced for all 154 test observations
- Probability outputs are valid
- Recorded evaluation metrics are reproducible

## Responsible AI

This project is an academic and portfolio machine-learning exercise.

**It is not a clinically validated diagnostic system and should not be used to
make medical decisions.**

Important limitations include the small dataset, limited holdout set, suspicious
zero values, lack of external validation, lack of prospective validation, and lack
of clinical calibration and utility analysis.

## Project Status

**Project 1 — Diabetes Diagnosis Prediction: COMPLETE**

Academic submission: **PASS**

Model integrity: **PASS**

Dataset integrity: **PASS**

Reproducibility: **PASS**

Professional packaging: **PASS**