# Predicting Student Dropout and Academic Success

## Executive Summary
This repository contains an end-to-end analysis and model comparison to predict student dropout and academic outcomes. The project evaluates multiple machine learning classifiers and a stacking ensemble to identify students at risk early so institutions can plan targeted interventions.

## Problem Statement
Educational institutions need reliable, interpretable models to detect students at risk of dropout or poor academic performance. This work compares several classifiers on a tabular student dataset and recommends practical deployment and improvement strategies.

## Dataset
- Full dataset description, preprocessing steps, feature engineering, target mapping, and train/test split are documented in `SML-mini-project.ipynb`.
- Target: multiclass labels {0, 1, 2} — see the notebook for exact label meanings.
- Reported evaluation metrics are computed on the held-out test set (885 samples).

## Models Evaluated
- Logistic Regression
- Decision Tree
- Random Forest
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Gradient Boosting
- XGBoost
- Stacking Classifier (ensemble)

All model training and per-model classification reports are available in `SML-mini-project.ipynb`.

## Results — Model Comparison (test set)
Summary (metrics taken from the notebook classification reports):

| Model | Accuracy | Weighted F1 | Macro F1 |
|---|---:|---:|---:|
| Stacking Classifier | 0.77 | 0.76 | 0.71 |
| Logistic Regression | 0.76 | 0.76 | 0.70 |
| Gradient Boosting | 0.76 | 0.75 | 0.69 |
| XGBoost | 0.76 | 0.75 | 0.69 |
| Random Forest | 0.75 | 0.75 | 0.70 |
| Decision Tree | 0.70 | 0.71 | 0.66 |
| KNN | 0.65 | 0.63 | 0.56 |
| SVM | 0.55 | 0.55 | 0.48 |

Notes:
- Values are copied from the test-set classification reports in `SML-mini-project.ipynb` (885 test samples).
- The Stacking Classifier achieves the highest accuracy (0.77) and the highest macro F1, though gains over the best single-models (Logistic Regression, Gradient Boosting, XGBoost) are modest.

## Key Inferences
1. Predictive signal: The dataset contains meaningful signal — most models achieve accuracy in the 0.70–0.77 range.
2. Top performers: Ensemble approaches (stacking, gradient boosting, XGBoost) and Logistic Regression are the most reliable on this dataset.
3. Hard-to-predict class: Label `1` is consistently the weakest across models (low precision/recall/F1). This indicates class imbalance and/or insufficient discriminative features for that group.
4. Model suitability: Tree-based ensembles and stacking handle mixed feature types and non-linear relationships well here; distance-based and margin-based methods (KNN, SVM) underperformed.
5. Practical trade-offs: If detecting the at-risk subgroup (label `1`) is critical, prioritize recall for that class via targeted techniques (resampling, class weights, threshold tuning).

## Recommendations (practical)
- Production candidate: Use the Stacking Classifier or a tuned XGBoost/GradientBoosting model for overall performance and robustness.
- Improve minority-class detection:
  - Rebalance the training data (SMOTE/ADASYN or targeted oversampling), or apply class weights during training.
  - Consider a two-stage approach: (A) binary classifier to flag “at-risk” vs “not at-risk”; (B) multiclass classifier for finer distinctions.
  - Perform threshold tuning and probability calibration to optimize recall versus precision based on operational cost.
- Interpretability: Generate SHAP explanations or permutation importances to communicate feature-level drivers to stakeholders.
- Validation: Use stratified k-fold cross-validation and report mean ± std for metrics to capture model variance.

## Next steps / Future work
- Hyperparameter optimization (Bayesian or randomized search) for each model.
- Calibrate probabilities and tune decision thresholds per business costs.
- Add temporal/longitudinal features if available to model student progression.
- Implement a lightweight deployment pipeline with monitoring and drift detection.

## How to reproduce
1. Open `SML-mini-project.ipynb` for the full data pipeline and evaluation code.
2. Use the same random seeds and the notebook’s train/test split to reproduce the reported numbers.
3. For production selection, run stratified k-fold CV and log metrics (MLflow or similar).

## Repo structure
- SML-mini-project.ipynb — Notebook with data preparation, models, and evaluation.
- README.md — This file.

## Ethics & Limitations
- Ensure data privacy and compliance with institution policies before deployment.
- Evaluate fairness across subgroups and monitor for disparate impacts.
- Treat model outputs as decision-support; combine with domain expertise and human review.

## Contribution & License
Contributions welcome. Open an issue or pull request describing changes. Add a license (e.g., MIT) if you intend to share this work publicly.
