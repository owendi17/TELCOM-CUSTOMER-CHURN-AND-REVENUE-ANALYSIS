# Telecom Customer Churn & Revenue Analysis

## Overview
This project analyzes customer churn and revenue patterns for a telecom company.  
Customer churn — when a customer leaves for a competitor — is a major source of lost revenue.  
The goal is to identify high-risk customers, understand churn drivers, and provide actionable insights for retention campaigns.

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

## Key Findings

![Churn Distribution](images/churn_distribution.png)  
*Figure 1: Churn vs Non-Churn customers*
<img width="580" height="453" alt="image" src="https://github.com/user-attachments/assets/d03812c2-bae1-4a54-bb02-0bf7a9cc4c3b" />

- Overall churn rate: ~26.5%  
- Month-to-month contracts and Fiber optic internet have higher churn rates.  
- Customers with higher `MonthlyCharges` and shorter tenure are at higher risk.  
- Top features influencing churn: `TotalCharges`, `MonthlyCharges`, `tenure`, `Contract type`, `PaymentMethod`.

![Monthly Charges vs Churn](images/monthly_charges_churn.png)  
*Figure 2: Monthly Charges vs Churn*

---

## Feature Engineering

- **RevenuePerMonth** — total charges divided by tenure.  
- **PhoneInternet** — interaction between phone service and fiber optic internet.  
- Categorical variables encoded for modeling.  

---

## Modeling & Evaluation

- Models used: Logistic Regression, Random Forest, XGBoost  
- Evaluated using accuracy, precision, recall, F1-score  
- Threshold tuning applied for better recall on churners

![Feature Importance](images/feature_importance.png)  
*Figure 3: Top 10 features influencing churn (Random Forest)*
<img width="902" height="545" alt="image" src="https://github.com/user-attachments/assets/060cc0fe-0b1b-4a46-b9a8-5a247d300009" />

**Performance Snapshot:**

| Model               | Accuracy | Recall (Churn) | F1-Score (Churn) |
|--------------------|----------|----------------|-----------------|
| Logistic Regression | 0.82     | 0.60           | 0.64            |
| Random Forest       | 0.80     | 0.49           | 0.57            |
| XGBoost             | 0.79     | 0.50           | 0.56            |

---

## Business Insights

- High-risk customers can be **prioritized for retention campaigns**.  
- Financial metrics (`RevenuePerMonth`, `MonthlyCharges`) and contract types are the **strongest predictors of churn**.  
- Insights can inform marketing, customer support, and pricing strategies.  

---

## Limitations

- Dataset is imbalanced: fewer churners than non-churners  
- Behavioral or usage data (e.g., support calls, service changes) not included  
- Static snapshot; temporal trends not analyzed  

---

## Next Steps

- Add more behavioral and service usage features  
- Explore temporal trends and subscription changes  
- Deploy a **churn risk scoring system** for retention campaigns  
- Link **Tableau dashboards** to this repo for interactive visualization  

---

## Tools & Libraries

- Python: `pandas`, `numpy`, `matplotlib`, `seaborn`  
- Machine learning: `scikit-learn`, `XGBoost`  
- Jupyter Notebook for analysis and visualization

