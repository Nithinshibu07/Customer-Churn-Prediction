# Customer Churn Prediction

## Project Overview

This project focuses on predicting customer churn for a telecommunications company using machine learning techniques. The goal is to identify customers who are likely to discontinue the service and uncover the key factors contributing to churn.

The insights generated from this project can help businesses implement proactive customer retention strategies and reduce revenue loss.

---

## Problem Statement

Customer churn is a critical business challenge in the telecommunications industry. Retaining existing customers is often more cost-effective than acquiring new ones. This project aims to build a predictive model that can identify customers at risk of churning and provide actionable business insights.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

**Records:** 7043 Customers

**Features:** 33 Customer-related attributes including:

* Demographics
* Service subscriptions
* Billing information
* Contract details
* Customer Lifetime Value (CLTV)

**Target Variable:**

* Churn Label (Yes / No)

---

## Project Workflow

1. Business Understanding
2. Data Understanding
3. Exploratory Data Analysis (EDA)
4. Data Cleaning
5. Feature Engineering
6. Model Development
7. Model Evaluation
8. Feature Importance Analysis
9. Customer Risk Segmentation
10. Business Recommendations

---

## Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* LightGBM

---

## Repository Structure

```text
customer-churn-prediction
│
├── data
│   ├── raw
│   └── processed
│
├── notebooks
│   └── Customer_Churn_Prediction.ipynb
│
├── reports
│   └── figures
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Current Progress

### Completed
- EDA
- Data Cleaning

### In Progress
- Feature Engineering

### Upcoming
- Model Training


---

## Key Findings from Exploratory Data Analysis

* Overall churn rate is 26.5%, indicating a moderate class imbalance.
* Customers with shorter tenure are significantly more likely to churn.
* Month-to-month contracts show the highest churn rates compared to long-term contracts.
* Fiber optic customers churn at a substantially higher rate than DSL customers.
* Customers with higher monthly charges are more likely to leave the service.
* Geographic attributes provide limited predictive value for churn.
* Contract type, tenure, and monthly charges emerged as the strongest churn indicators.

---

## Future Enhancements

* Advanced Feature Engineering
* Hyperparameter Tuning
* Customer Risk Scoring
* Retention Strategy Recommendations
