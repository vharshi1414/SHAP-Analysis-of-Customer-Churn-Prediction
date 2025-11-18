# Interpretable Machine Learning: SHAP Analysis of Customer Churn Prediction

This project implements a fully interpretable machine-learning system for predicting telecom customer churn using **XGBoost**, **Random Forest**, and **SHAP (SHapley Additive exPlanations)**.  
It demonstrates not only high predictive performance but also **explainability**, allowing business teams to understand *why* customers churn and how to reduce it.

---

## Project Objectives

According to the assignment requirements, this project demonstrates:

1. **Complete data preprocessing**  
   - Missing value handling  
   - Encoding categorical variables  
   - Feature scaling and feature engineering  
   - Creation of churn-related features  

2. **Training of at least two ML models**  
   - XGBoost  
   - Random Forest  
   - 5-fold cross-validation  
   - Hyperparameter tuning with GridSearchCV  

3. **Interpretability using SHAP**  
   - Global explanations (summary plots + bar plots)  
   - Local explanations for 3-5 individual customers  
   - Force plots + waterfall fallbacks  

4. **Actionable business insights**  
   - Top churn drivers  
   - Direction of influence (increase/decrease churn)  
   - Executive summary for stakeholders  

---

## Dataset

Dataset: **Telco Customer Churn**  
Source: Provided in project instructions.

Key fields include:
- Customer demographics  
- Subscription attributes  
- Monthly & total charges  
- Tenure  
- Churn (Yes/No)  

Target variable is converted to **0 (No)** and **1 (Yes)**.

---

##  Feature Engineering

Steps performed:

- Converted `TotalCharges` to numeric  
- Created **tenure groups** (0–6, 6–12, etc.)  
- Added interaction feature:  
  - `AvgMonthlyValue = tenure × MonthlyCharges`
- Removed ID-like fields  

---

##  Model Training

Two models were trained:

### **1. Random Forest Classifier**  
- Tuned using GridSearchCV  
- Evaluated using ROC-AUC  

### **2. XGBoost Classifier**  
- Used class weighting (`scale_pos_weight`) for imbalance  
- Tuned using GridSearchCV  
- Evaluated using ROC-AUC  

### **Model Selection**  
Best model is chosen automatically based on **highest CV AUC**.

---

##  Performance Metrics (Test Set)

The pipeline outputs:

- Accuracy  
- ROC AUC  
- Precision  
- Recall  
- F1-score  
- Best probability threshold  

All stored in:

<a href = "https://github.com/vharshi1414/SHAP-Analysis-of-Customer-Churn-Prediction/commit/9b6a5fb3538e99247e34ccaf1c51afc15fa039a7"> Test_metrics </a> /n
<a href = "https://github.com/vharshi1414/SHAP-Analysis-of-Customer-Churn-Prediction/blob/main/test_predictions.csv"> Test_predictions </a>
