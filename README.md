# Telecom Customer Churn & Revenue Analysis

## Overview
This project analyzes customer churn and revenue patterns for a telecom company.  
Customer churn — when a customer leaves for a competitor — is a major source of lost revenue. This analysis aims to identify high-risk customers, understand churn drivers, and provide actionable insights for retention campaigns.

---

## Dataset
The dataset is the [Telco Customer Churn dataset](https://www.kaggle.com/blastchar/telco-customer-churn) from Kaggle.  

**Key attributes include:**
- Customer demographics: `gender`, `SeniorCitizen`, `Partner`, `Dependents`  
- Account info: `tenure`, `Contract`, `PaperlessBilling`, `PaymentMethod`  
- Services subscribed: `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`  
- Charges: `MonthlyCharges`, `TotalCharges`  
- Target: `Churn` (Yes/No)

---

## Objectives
1. Clean and preprocess the data.  
2. Engineer meaningful features such as `RevenuePerMonth` and service interactions.  
3. Explore data to uncover patterns in churn.  
4. Build and evaluate machine learning models to predict churn.  
5. Identify key drivers of churn and actionable insights for business decisions.

---

## Key Findings
- Churn rate: ~26.5% of customers churn.  
- Month-to-month contracts and Fiber optic internet have higher churn rates.  
- Customers with higher `MonthlyCharges` and short tenure are at higher risk.  
- Logistic Regression achieved the best performance in predicting churn with recall ~0.60 for churners.  
- Top features influencing churn: `TotalCharges`, `MonthlyCharges`, `tenure`, `Contract type`, `PaymentMethod`.

---

## Features Engineered
- `RevenuePerMonth` — total charges divided by tenure.  
- `PhoneInternet` — interaction between phone service and fiber optic internet.  
- Categorical variables encoded for modeling.  

---

## Modeling
- Models used: Logistic Regression, Random Forest, XGBoost.  
- Evaluated using accuracy, precision, recall, F1-score.  
- Threshold tuning applied for better recall on churners.  

---

## Business Insights
- High-risk customers can be prioritized for retention campaigns.  
- Financial metrics (`RevenuePerMonth`, `MonthlyCharges`) and contract types are the strongest predictors of churn.  
- Insights can inform marketing, customer support, and pricing strategies.  

---

## Limitations
- Dataset is imbalanced: fewer churners than non-churners.  
- Behavioral or usage data (e.g., support calls, service changes) not included.  
- Static snapshot; temporal trends not analyzed.  

---

## Next Steps
- Add more behavioral and service usage features.  
- Explore temporal trends and subscription changes.  
- Deploy a churn risk scoring system for retention campaigns.  

---

## Tools & Libraries
- Python (pandas, numpy, matplotlib, seaborn)  
- Machine learning: scikit-learn, XGBoost  
- Jupyter Notebook for analysis and visualization
