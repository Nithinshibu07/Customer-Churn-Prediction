# Customer Churn Prediction

## Project Overview

This project focuses on predicting customer churn for a telecommunications company using machine learning techniques. The objective is to identify customers who are likely to discontinue their services and understand the factors that contribute to customer attrition.

The insights generated from this project can help businesses improve customer retention strategies and reduce customer loss.

---

## Business Problem

Customer churn is one of the most significant challenges faced by subscription-based businesses. Identifying customers who are likely to leave allows organizations to take proactive actions through targeted retention campaigns and personalized offers.

The goal of this project is to build a machine learning model capable of predicting customer churn and identifying the key drivers behind customer departures.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

**Total Records:** 7,043 Customers

**Target Variable:**

* Churn Label (Yes / No)

### Dataset Features

The dataset contains information related to:

* Customer demographics
* Service subscriptions
* Internet services
* Billing information
* Contract details
* Payment methods
* Customer lifetime information

---

## Project Workflow

1. Data Understanding
2. Data Cleaning
3. Exploratory Data Analysis (EDA)
4. Feature Engineering
5. Data Preprocessing
6. Model Development
7. Cross Validation
8. Class Imbalance Handling
9. Hyperparameter Tuning
10. Model Evaluation
11. Model Selection

---

## Exploratory Data Analysis

Key observations obtained during EDA:

* Overall churn rate is approximately 26.5%.
* Customers with shorter tenure are more likely to churn.
* Customers paying higher monthly charges show a greater tendency to churn.
* Month-to-month contracts exhibit the highest churn rate.
* Fiber optic customers have higher churn rates compared to other internet service types.
* Longer customer tenure is associated with lower churn probability.

---

## Data Cleaning

The following preprocessing steps were performed:

* Missing value analysis
* Duplicate record verification
* Data type corrections
* Removal of irrelevant features
* Removal of target leakage variables

### Features Removed

* CustomerID
* Count
* Country
* State
* City
* Zip Code
* Lat Long
* Latitude
* Longitude
* Churn Value
* Churn Score
* CLTV
* Churn Reason

These variables were removed because they were either identifiers, high-cardinality location fields, or potential sources of target leakage.

---

## Feature Engineering

To improve predictive performance, several business-driven features were created.

### Tenure Group

Customers were grouped according to subscription duration:

| Group       | Tenure Range |
| ----------- | ------------ |
| New         | 0–12 Months  |
| Growing     | 13–24 Months |
| Established | 25–48 Months |
| Loyal       | 49–72 Months |

### Service Count

The total number of subscribed services was calculated using:

* Phone Service
* Multiple Lines
* Online Security
* Online Backup
* Device Protection
* Tech Support
* Streaming TV
* Streaming Movies

### Auto Payment

A binary feature indicating whether the customer uses an automatic payment method.

---

## Data Preprocessing

The following preprocessing techniques were applied:

* Target variable encoding
* One-hot encoding
* Feature scaling using StandardScaler
* Stratified train-test split
* Class imbalance handling using SMOTE

---

## Cross Validation

Two machine learning models were evaluated using 5-Fold Stratified Cross Validation.

### Cross Validation Results

| Model         | ROC-AUC |
| ------------- | ------: |
| Random Forest |   0.836 |
| LightGBM      |   0.854 |

### Observation

Both models demonstrated strong predictive performance during cross-validation.

LightGBM achieved the highest average ROC-AUC score and Random Forest delivered comparable results, making both models suitable candidates for further optimization.

---

## Hyperparameter Tuning

Hyperparameter optimization was performed using RandomizedSearchCV.

### Tuned Models

* Random Forest Classifier
* LightGBM Classifier

The objective was to maximize ROC-AUC while improving generalization performance.

---

## Final Model Evaluation

After tuning, both models were evaluated on the unseen test dataset.

### Model Comparison

| Model         | F1 Score | ROC-AUC |
| ------------- | -------: | ------: |
| Random Forest |   0.6077 |  0.8298 |
| LightGBM      |   0.6063 |  0.8274 |

### Model Selection Strategy

The final model was selected using:

1. Highest F1 Score
2. Highest ROC-AUC Score (used only if F1 Scores were tied)

Since Random Forest achieved the highest F1 Score, it was selected as the final model.

---

## Final Model Performance

### Selected Model

**Random Forest Classifier**

### Test Set Metrics

| Metric    |  Score |
| --------- | -----: |
| Accuracy  | 0.7764 |
| Precision | 0.5688 |
| Recall    | 0.6524 |
| F1 Score  | 0.6077 |
| ROC-AUC   | 0.8298 |

### Classification Summary

The model successfully identifies a significant proportion of churn customers while maintaining reasonable precision.

The recall score indicates that approximately 65% of churning customers are correctly identified, making the model useful for customer retention initiatives.

---

## Feature Importance

The most influential features contributing to churn prediction include:

* Contract Type
* Tenure Months
* Monthly Charges
* Total Charges
* Internet Service

These variables have the strongest impact on customer churn behavior.

---

## Tools and Technologies

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* LightGBM
* Imbalanced-learn

### Development Environment

* Google Colab
* Jupyter Notebook

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
│   └── plots
│
├── README.md
└── requirements.txt
```

---

## Current Progress

### Completed

* Data Understanding
* Data Cleaning
* Exploratory Data Analysis
* Feature Engineering
* Data Preprocessing
* Cross Validation
* SMOTE Implementation
* Hyperparameter Tuning
* Model Evaluation
* Final Model Selection
* Feature Importance Analysis

### Next Steps

* Model Serialization
* New Customer Prediction Workflow
* Business Recommendations
* Project Conclusion

---

This project demonstrates a complete machine learning workflow for customer churn prediction, covering data preparation, exploratory analysis, feature engineering, model optimization, evaluation, and final model selection.
