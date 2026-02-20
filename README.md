

# Age Prediction Model (Phitron Contest)

This project implements an end-to-end machine learning pipeline to predict age using structured tabular data. The solution combines multiple models with blending and cross-validation techniques to improve prediction accuracy.

---

## Project Overview

- Built a machine learning pipeline using Scikit-learn and CatBoost.
- Applied feature preprocessing including scaling and categorical encoding.
- Used K-Fold Cross Validation for robust evaluation.
- Combined Huber Regressor and CatBoost using weighted blending.
- Optimized predictions using quantile-based adjustment and clipping.

---

## Models Used

### 1️. Huber Regressor
- Robust linear regression model.
- Resistant to outliers.
- Implemented within Scikit-learn Pipeline.

### 2️. CatBoost Regressor
- Gradient boosting algorithm optimized for categorical features.
- Loss function: MAE
- Iterations: 1200
- Learning Rate: 0.03
- Depth: 5

---

## Data Processing

- Numerical features scaled using StandardScaler.
- Categorical features encoded using OneHotEncoder.
- ColumnTransformer used for preprocessing pipeline.

---

## Cross Validation

- KFold (5 splits)
- Out-of-fold predictions generated.
- Test predictions averaged across folds.

---

##  Model Blending

Predictions from both models were blended:

Final Prediction = w * CatBoost + (1 - w) * Huber

Best weight found using grid search:

- Best Weight: 0.83
- MAE Score: ~1.328
- Contest S MAE Score:  ~1.269

---

## Post-processing

- Quantile alignment applied.
- Predictions clipped between valid age range (1–29).

---

## Technologies Used

- Python
- Scikit-learn
- CatBoost
- Pandas
- NumPy

---

## How to Run

1. Clone repository:

```bash
https://github.com/Foysal348/Crab-Age-Prediction-with-Highest-Score.git
