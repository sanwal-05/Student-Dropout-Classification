# Predicting Student Dropout and Academic Success using Machine Learning

## 📌 Project Overview
Student dropout is a critical challenge in higher education that impacts individual careers and institutional reputations. This project develops advanced machine learning-based predictive systems to identify at-risk students early, enabling timely institutional interventions to improve retention and graduation rates.

---

## 🚀 Objectives
*   **Classification:** Build robust models to predict student outcomes (Dropout, Enrolled, Graduate).
*   **Feature Analysis:** Identify the key predictors influencing academic success or failure.
*   **Algorithmic Comparison:** Evaluate multiple machine learning algorithms, including ensemble and deep learning approaches.
*   **Performance Targets:** Achievement of F1-Score ≥ 0.85 and Dropout Recall ≥ 0.80.

---

## 📊 Dataset Information
*   **Source:** [UCI Machine Learning Repository (Dataset ID: 697)](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)
*   **Feature Categories:**
    *   Academic Performance (Grades, Credits)
    *   Admission Details (Prior education, application mode)
    *   Demographics (Age, Gender)
    *   Socioeconomic Factors (Scholarship status, parents' occupation)
    *   Engagement Metrics

---

## 🛠️ Technology Stack
*   **Language:** Python
*   **Data Processing:** Pandas, NumPy, Scikit-learn
*   **Visualization:** Matplotlib, Seaborn
*   **Machine Learning:** Scikit-learn, XGBoost
*   **Deep Learning:** TensorFlow (Keras)

---

## 📈 Model Performance
We evaluated 10 different models, ranging from traditional classifiers to deep learning architectures:

| Model | Accuracy | F1-Score | Precision | Recall |
| :--- | :--- | :--- | :--- | :--- |
| **XGBoost (Best)** | **~0.85** | **~0.85** | **~0.85** | **~0.85** |
| Random Forest | ~0.84 | ~0.84 | ~0.84 | ~0.84 |
| Gradient Boosting| ~0.84 | ~0.84 | ~0.84 | ~0.84 |
| Neural Network | ~0.82 | ~0.82 | ~0.82 | ~0.82 |
| Stacking Classifier| ~0.84 | ~0.84 | ~0.84 | ~0.84 |

*Note: Specific values vary slightly per run, but XGBoost consistently emerged as the top performer.*

---

## 🔍 Key Insights
1.  **Academic performance** (specifically credits earned) is the strongest predictor of student outcomes.
2.  **Socioeconomic factors** such as scholarship status significantly impact graduation rates.
3.  **Traditional ML models** (XGBoost/Random Forest) often outperform Deep Learning for this tabular dataset.

---

## 🔮 Future Scope
The project has several avenues for further development:
*   **Enhanced Data Collection:** Incorporating qualitative factors like mental health benchmarks and granular student engagement metrics.
*   **Temporal Modeling:** Implementing LSTM or RNN architectures to track student progress over time rather than a static snapshot.
*   **Explanability (XAI):** Using SHAP or LIME to provide advisors with clear reasons why a specific student is flagged as "at-risk."
*   **Causal Inference:** Moving beyond correlation to understand the structural causes of dropout.
*   **Real-world Deployment:** Developing a dashboard for institutional advisors and conducting A/B testing on intervention strategies.
*   **Cross-Institutional Validation:** Testing the model's generalizability across different universities and education systems.

---

## ⚖️ Ethical Considerations
*   **Fairness:** Regular audits to ensure no bias against specific demographic groups.
*   **Transparency:** Providing explainable results to students and staff.
*   **Action-Oriented:** Using predictions to support and guide students, rather than for punitive measures.

---

## 📁 Repository Structure
*   `SML-miniproject.ipynb`: Main project notebook containing EDA, preprocessing, and model training.
*   `01_target_distribution.png` - `08_feature_importance_best_model.png`: Visual artifacts generated during analysis.

---
**Supervised Learning | Mini Project | 2026**
