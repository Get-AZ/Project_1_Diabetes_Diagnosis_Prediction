# Interview Preparation — Diabetes Diagnosis Prediction

## 1. Give me a 60-second explanation of the project.

I built a binary-classification project to predict the diabetes outcome in a dataset
with 768 observations and eight predictive features.

I first performed data-quality and exploratory analysis, paying particular attention
to physiologically suspicious zero values. I then compared a straightforward baseline
Logistic Regression pipeline against a clinically motivated preprocessing pipeline.

The baseline performed better on the held-out test set, achieving approximately
0.823 ROC-AUC, so I selected it as the champion. I then performed coefficient-based
explainability, threshold analysis, model serialization, and independent reproducibility
validation.

The final artifact and dataset were SHA256 validated.

I would emphasize that this is an academic portfolio project and not a clinically
validated diagnostic system.

## 2. Why Logistic Regression?

Logistic Regression was appropriate because this is a binary classification problem
and the model provides useful interpretability.

It also produces probability estimates, allowing threshold behavior to be analyzed.

## 3. Why compare two preprocessing pipelines?

Several physiological variables contain zero values that may be clinically suspicious.
Instead of silently changing them, I compared a baseline approach against a pipeline
that treated those values as missing and applied median imputation.

The baseline performed better, so I selected it rather than assuming the more complex
pipeline was automatically superior.

## 4. How did you prevent data leakage?

The train/test split was performed before model fitting.
The test set contained 154 observations and was not used to fit the model.
Learned preprocessing parameters came from the training data.

## 5. Why ROC-AUC?

ROC-AUC evaluates discrimination across classification thresholds.
It was useful because threshold selection was treated as a separate analysis.

However, ROC-AUC alone is not sufficient for clinical decision-making.

## 6. Why not optimize only accuracy?

Accuracy can hide class-specific behavior.
I therefore evaluated accuracy, precision, recall, F1, and ROC-AUC.

## 7. What did threshold analysis show?

Threshold 0.25 produced the highest observed recall and F1 within the tested grid.

However, I did not select 0.25 as a clinical threshold because clinical operating-point
selection requires intended-use definition, error-cost analysis, calibration, and
appropriate validation.

## 8. What did explainability show?

Glucose had the strongest positive Logistic Regression coefficient, followed by BMI
and Pregnancies.

Because the features were standardized, the coefficients describe changes in model
log-odds associated with standardized feature changes.

They should not be interpreted as causal medical relationships.

## 9. What is the biggest limitation?

The dataset is relatively small and evaluation is based on a single held-out test set
of 154 observations.

There was no external or prospective clinical validation.

Therefore, the reported performance demonstrates academic model behavior rather than
clinical effectiveness.

## 10. How did you prove reproducibility?

I saved the final model as a joblib artifact and independently loaded it.
I validated the pipeline structure, feature count, predictions, probabilities, and
recorded evaluation metrics.

I also compared SHA256 hashes against the recorded evidence.

Model SHA256: `5db1b088d1bfb18c74c9e7622e013c4258759f9f6f9e34a6a4d4398f8febba9c`

Dataset SHA256: `698c203a14aa31941d2251175330c9199f3ccdb31597abbba2a3e35416257a72`

## 11. What would you require before real-world deployment?

I would require external validation, representative validation data, calibration
assessment, prospective evaluation, clinical stakeholder review, error-cost analysis,
fairness and subgroup analysis, privacy/security review, monitoring, and appropriate
governance or regulatory review.

## 12. What would you improve next?

- Cross-validation
- Calibration analysis
- External validation
- Alternative classifier comparison
- Robust missing-value treatment
- Subgroup performance analysis
- Experiment tracking
- Containerized inference
- Monitoring

## Strong Interview Closing Statement

The strongest engineering lesson from this project is that machine learning is not
just model fitting. I treated the project as a reproducible system: I validated the
data, compared preprocessing strategies, evaluated multiple metrics, explained the model,
analyzed thresholds, serialized the final artifact, independently reproduced its results,
and cryptographically verified the model and dataset.

That gives me a strong foundation for progressing from classical machine learning into
MLOps and cloud-based ML systems.