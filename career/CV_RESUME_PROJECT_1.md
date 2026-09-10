# CV / Resume Entry — Project 1

## Diabetes Diagnosis Prediction | Python, scikit-learn, Logistic Regression

- Developed a reproducible binary-classification pipeline to predict diabetes outcomes
  from an 8-feature dataset containing 768 observations.
- Achieved **0.823 ROC-AUC, 0.714 accuracy, 0.609 precision,
  0.518 recall, and 0.560 F1** on a stratified 20% held-out test set.
- Compared baseline and clinically motivated preprocessing approaches and selected
  Logistic Regression as the champion based on holdout performance.
- Performed coefficient-based model explainability and probability-threshold analysis
  to evaluate precision/recall trade-offs.
- Built a reproducibility and artifact-integrity workflow using serialized model artifacts,
  independent validation, and SHA256 hashes.
- Documented responsible-AI limitations and explicitly distinguished academic model
  performance from clinical validation.

### Technology

Python · pandas · NumPy · scikit-learn · Logistic Regression · StandardScaler ·
SimpleImputer · Model Evaluation · Explainability · Reproducibility · SHA256