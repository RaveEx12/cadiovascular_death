# Cardiovascular Risk Prediction Model Notebook Summary

---

## Overview

This notebook demonstrates the process of building and evaluating a machine learning model to predict cardiovascular risk using a dataset with various features related to patient health and demographics. The primary goal is to identify the best-performing model through thorough preprocessing, feature engineering, and model evaluation steps.

## Data Preprocessing

### Handling Missing Values
- **Missing Values Treatment:** The dataset was checked for missing values, and appropriate methods were employed to handle them.

### Feature Engineering
- **Categorical Features:** Categorical features were encoded using the CatBoostEncoder.
- **Numerical Features:** Numerical features were transformed using the Yeo-Johnson transformer to handle non-normal distributions and improve model performance.

### Outlier Detection
- **Outlier Detection Method:** Initially, the IQR method was used to remove outliers. Despite this, some outliers were still present, suggesting the need for further tuning or an alternative method like IsolationForest for better outlier treatment.

## Model Building

### Pipeline Construction
A machine learning pipeline was constructed to streamline the preprocessing and modeling steps. The pipeline consisted of:
- **Preprocessing Steps:**
  - Yeo-Johnson transformation for numerical features.
  - CatBoostEncoder for categorical features.
- **Model:** Various regression models were tested, including CatBoostRegressor and LightGBMRegressor.

## Model Evaluation

### CatBoost Regressor
- **Validation Curve:** The validation curve for the CatBoost model showed that the model's performance improved with increased complexity but started to plateau, indicating potential overfitting beyond a certain point.
- **Learning Curve:** The learning curve indicated that CatBoost had a good fit, but there was room for improvement in generalization.

### LightGBM Regressor
- **Validation Curve:** LightGBM displayed a more stable and consistent improvement in performance as the number of training examples increased.
- **Learning Curve:** The learning curve for LightGBM showed that it generalized better than CatBoost with less variance between training and validation scores.

### Performance Metrics
- **RMSE and R2 Score:** Both models were evaluated using RMSE and R2 score. LightGBM outperformed CatBoost in both metrics, showing lower RMSE and higher R2 scores, indicating better predictive accuracy and generalization.

## Model Selection
Based on the evaluation, **LightGBM** was chosen as the final model for this project due to its superior performance in terms of generalization and accuracy, as demonstrated by the learning and validation curves, as well as the RMSE and R2 scores.

## Conclusion
The notebook provides a comprehensive workflow for building a predictive model for cardiovascular risk. The chosen model, LightGBM, demonstrated robust performance and generalization capability. Future work can focus on further hyperparameter tuning, alternative outlier detection methods, and exploring additional features for improved accuracy.