# Thyroid Disease Detection using Machine Learning
---

## Project Objective

To **accurately detect thyroid disorders** (hypothyroidism, hyperthyroidism, and normal) using machine learning algorithms on a real-world medical dataset. The project leverages advanced data preprocessing, feature engineering, and robust model evaluation to improve diagnostic support for healthcare professionals.

---

## Overview

- **Dataset Source**: UCI Machine Learning Repository (Modified by Goldstein Markus et al.)
- **Records**: 9,172 patient entries
- **Attributes**: 31 features including demographics, medical history, lab test results

#### Key Attributes:
**1. Demographic Information:**
- *Age:* The age of the patient (integer).
- *Sex:* Gender identification of the patient (string).

**2. Medical History:**
- *On_thyroxine:* Boolean indicating whether the patient is on thyroxine.
- *Query_on_thyroxine:* Boolean indicating queries regarding thyroxine usage.
- *On_antithyroid_meds:* Boolean indicating whether the patient is on antithyroid medications.
- *Sick:* Boolean indicating whether the patient is sick.
- *Pregnant:* Boolean indicating whether the patient is pregnant.
- *Thyroid_surgery:* Boolean indicating whether the patient has undergone thyroid surgery.
- *I131_treatment:* Boolean indicating whether the patient is undergoing I131 treatment.
- *Query_hypothyroid:* Boolean indicating the patient's belief of having hypothyroidism.
- *Lithium:* Boolean indicating whether the patient uses lithium.
- *Goitre:* Boolean indicating whether the patient has goitre.
- *Tumor:* Boolean indicating whether the patient has a tumor.
- *Hypopituitary:* Float value indicating a condition related to the hyperpituitary gland.
- *Psych:* Boolean indicating a psychological condition.

**3. Laboratory Test Results:**
- *TSH_measured:* Boolean indicating whether TSH was measured.
- *TSH:* Float value representing the TSH level in the blood.
- *T3_measured:* Boolean indicating whether T3 was measured.
- *T3:* Float value representing the T3 level in the blood.
- *TT4_measured:* Boolean indicating whether TT4 was measured.
- *TT4:* Float value representing the TT4 level in the blood.
- *T4U_measured:* Boolean indicating whether T4U was measured.
- *T4U:* Float value representing the T4U level in the blood.
- *FTI_measured:* Boolean indicating whether FTI was measured.
- *FTI:* Float value representing the FTI level in the blood.
- *TBG_measured:* Boolean indicating whether TBG was measured.
- *TBG:* Float value representing the TBG level in the blood.

**4. Other Attributes:**
- *Referral_source:* String indicating the source of patient referral.
- *Target:* String indicating the medical diagnosis of hyperthyroidism.
- *Patient_id:* String representing a unique identifier for each patient.

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

---

### Reference
- [1] Goldstein M, Uchida S. A comparative evaluation of unsupervised anomaly detection algorithms for multivariate data[J]. PloS one, 2016, 11(4): e0152173.
- [2] Schiffmann W, Joost M, Werner R. Synthesis and performance analysis of multilayer neural network architectures[J]. 1992.
- [3] Goldstein, Markus, 2015, "annthyroid-unsupervised-ad.tab", Unsupervised Anomaly Detection Benchmark, https://doi.org/10.7910/DVN/OPQMVF/CJURKL, Harvard Dataverse, V1, UNF:6:jJUwpBJ4iBlQto8WT6zsUg== [fileUNF]
