# Thyroid Disease Detection using Machine Learning
---

## Project Objective

To **accurately detect thyroid disorders** (hypothyroidism, hyperthyroidism, and normal) using machine learning algorithms on a real-world medical dataset. The project leverages advanced data preprocessing, feature engineering, and robust model evaluation to improve diagnostic support for healthcare professionals.

---

## Overview

- **Dataset Source**: UCI Machine Learning Repository (Modified by Goldstein Markus et al.)
- **Records**: 9,172 patient entries
- **Attributes**: 31 features including demographics, medical history, lab test results

---

## Methodology

### Data Preprocessing
- Handled missing values using **mean, median, and mode**
- Outlier detection using **3σ rule and IQR**
- One-hot encoding for categorical variables
- MinMax scaling for numerical features
- Dropped irrelevant columns: `patient_id`, `TBG`

### Exploratory Data Analysis (EDA)
- Distribution analysis of lab values (TSH, T3, TT4, etc.)
- Correlation heatmaps and feature importance
- Data imbalance handled via **stratified splitting**

### Models Trained
| Model              | Accuracy | Precision | Recall | F1 Score |
|-------------------|----------|-----------|--------|----------|
| Decision Tree      | 0.9785   | 0.9778    | 0.9785 | 0.9778   |
| KNN                | 0.9147   | 0.9072    | 0.9147 | 0.8984   |
| Random Forest      | 0.9870   | 0.9866    | 0.9870 | 0.9866   |
| Gradient Boosting  | **0.9889** | 0.9889 | 0.9889 | 0.9889   |
| SVM                | 0.8958   | 0.9033    | 0.8958 | 0.8587   |

---

## Feature Engineering

- Selected top features using **SHAP**, Random Forest importance, and correlation matrix
- Final features included: `age`, `sex_M`, `TSH`, `T3`, `TT4`, `FTI`, `T4U`, `on_thyroxine_t`

---

## Tools & Technologies

| Category         | Tools Used                           |
|------------------|--------------------------------------|
| Programming      | Python, Pandas, NumPy, Scikit-learn  |
| Visualization    | Matplotlib, Seaborn                  |
| Modeling         | RandomForest, SVM, KNN, XGBoost      |
| Evaluation       | GridSearchCV, Stratified K-Fold CV   |
| Deployment       | Pickled Model (`RandomForest.pkl`)   |
| IDE              | Jupyter Notebook / Google Colab      |

---

## Model Deployment (Future Scope)

- Convert final model (`RandomForest.pkl`) into a Flask-based web API
- Add real-time patient input form for quick diagnosis
- Deploy to cloud (Heroku / GCP)

---

## Impact

This system enhances early diagnosis of thyroid dysfunction, helping doctors:
- Differentiate between hypothyroid and hyperthyroid conditions
- Analyze key hormonal patterns
- Make timely, data-driven decisions for patient care
