# Customer Churn Prediction

## Project Overview

This project focuses on predicting customer churn for a telecommunications company using machine learning techniques. The objective is to identify customers who are likely to discontinue their services and uncover the key factors influencing churn behavior.

The insights generated from this project can help businesses improve customer retention strategies and reduce revenue loss.

---

## Business Problem

Customer churn is a major challenge in the telecommunications industry. Retaining existing customers is often more cost-effective than acquiring new ones.

This project aims to develop a machine learning model capable of predicting customer churn and identifying the factors that contribute most to customer attrition.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

**Total Records:** 7,043 Customers

**Target Variable:**

- Churn Label (Yes / No)

### Dataset Includes

- Customer demographics
- Service subscriptions
- Internet services
- Billing information
- Contract details
- Payment methods
- Customer lifetime value metrics

---

## Project Workflow

1. Business Understanding
2. Data Understanding
3. Exploratory Data Analysis (EDA)
4. Data Cleaning
5. Feature Engineering
6. Data Preprocessing
7. Model Development
8. Model Comparison
9. Model Evaluation
10. Feature Importance Analysis
11. Business Recommendations

---

## Key Findings from Exploratory Data Analysis

- Overall churn rate is approximately **26.5%**.
- Customers with shorter tenure are more likely to churn.
- Month-to-month contracts show significantly higher churn rates.
- Fiber optic customers exhibit higher churn than DSL customers.
- Customers with higher monthly charges tend to churn more frequently.
- Contract type, tenure, and monthly charges emerged as strong churn indicators.

---

## Data Cleaning

The following data cleaning steps were performed:

- Missing value analysis
- Duplicate record verification
- Data type corrections
- Removal of irrelevant and leakage-prone features

### Removed Features

- CustomerID
- Count
- Country
- State
- City
- Zip Code
- Lat Long
- Latitude
- Longitude
- Churn Value
- Churn Score
- Churn Reason
- CLTV

---

## Feature Engineering

Several business-driven features were created to improve model performance and better represent customer behavior.

### Tenure Group

Customers were categorized based on their subscription duration:

| Group | Tenure Range |
|---------|------------|
| New | 0–12 Months |
| Growing | 13–24 Months |
| Established | 25–48 Months |
| Loyal | 49–72 Months |

### Service Count

Calculated the total number of active services subscribed by each customer, including:

- Phone Service
- Multiple Lines
- Online Security
- Online Backup
- Device Protection
- Tech Support
- Streaming TV
- Streaming Movies

### Auto Payment

Binary feature indicating whether the customer uses an automatic payment method.

### Security Bundle

Binary feature indicating whether the customer subscribes to both:

- Online Security
- Tech Support

---

## Data Preprocessing

The following preprocessing techniques were applied:

- Target variable encoding
- Binary encoding
- One-hot encoding
- Feature scaling using StandardScaler
- Train-test split
- Class imbalance handling using SMOTE

---

## Models Evaluated

The following machine learning models were evaluated using 5-fold cross-validation and F1-score:

| Model | Mean F1 Score |
|---------|---------:|
| Random Forest | 0.857 |
| LightGBM | 0.838 |
| XGBoost | 0.837 |
| Logistic Regression | 0.820 |

### Current Best Model

**Random Forest Classifier**

Mean Cross-Validated F1 Score: **0.857**

---

## Evaluation Metrics

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC Score
- Confusion Matrix

Special emphasis is placed on Recall and F1-Score to effectively identify customers at risk of churn.

---

## Tools and Technologies

### Programming Language

- Python

### Libraries

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- LightGBM
- XGBoost
- Imbalanced-learn

### Development Environment

- Google Colab
- Jupyter Notebook

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
└── requirements.txt
```

---

## Current Progress

### Completed

- Business Understanding
- Data Understanding
- Exploratory Data Analysis (EDA)
- Data Cleaning
- Feature Engineering
- Data Preprocessing
- Model Development
- Model Comparison
-Final Model Evaluation
- Feature Importance Analysis

### Upcoming

- Business Recommendations
- Project Conclusion

---

## Future Enhancements

- Hyperparameter Tuning
- Ensemble Modeling
- Customer Risk Scoring
- Streamlit Deployment
- Interactive Dashboard

---


This project demonstrates an end-to-end machine learning workflow, from business understanding and exploratory analysis to predictive modeling and actionable business insights.
