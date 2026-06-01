# Customer Churn Prediction

## Project Overview

This project focuses on predicting customer churn for a telecommunications company using machine learning techniques. The objective is to identify customers who are likely to discontinue their services and uncover the key factors influencing churn behavior.

By proactively identifying at-risk customers, businesses can implement targeted retention strategies, improve customer satisfaction, and reduce revenue loss.

---

## Business Problem

Customer churn is a significant challenge in the telecommunications industry. Acquiring new customers is often more expensive than retaining existing ones. Therefore, understanding churn patterns and predicting potential churners is critical for business growth and profitability.

This project aims to develop a robust machine learning model capable of predicting customer churn and generating actionable business insights.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

**Total Records:** 7,043 Customers

**Target Variable:**

* Churn Label (Yes / No)

### Dataset Features

The dataset contains customer-related information including:

* Customer demographics
* Service subscriptions
* Internet services
* Billing information
* Contract details
* Payment methods
* Customer lifetime value metrics

---

## Project Workflow

1. Business Understanding
2. Data Understanding
3. Exploratory Data Analysis (EDA)
4. Data Cleaning
5. Feature Engineering
6. Data Preprocessing
7. Model Development
8. Model Evaluation
9. Feature Importance Analysis
10. Customer Risk Segmentation
11. Business Recommendations

---

## Exploratory Data Analysis Highlights

Key insights discovered during EDA:

* Overall churn rate is approximately 26.5%, indicating moderate class imbalance.
* Customers with shorter tenure are significantly more likely to churn.
* Month-to-month contracts exhibit the highest churn rates.
* Fiber optic customers churn at a higher rate than DSL customers.
* Customers with higher monthly charges tend to have higher churn probability.
* Geographic attributes provide limited predictive value.
* Contract type, tenure, and monthly charges emerged as strong churn indicators.

---

## Data Cleaning

The following preprocessing steps were performed:

### Missing Values

* Identified and analyzed missing values.
* Converted `Total Charges` to numeric format.
* Replaced invalid values with appropriate defaults.

### Duplicate Records

* Verified duplicate customer records.

### Feature Selection

Removed columns that provided limited predictive value or could introduce data leakage:

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
* Churn Reason
* CLTV

---

## Feature Engineering

Several business-driven features were created to enhance predictive performance and better represent customer behavior.

### 1. Tenure Group

Customers were segmented based on subscription duration:

| Group       | Tenure Range |
| ----------- | ------------ |
| New         | 0–12 Months  |
| Growing     | 13–24 Months |
| Established | 25–48 Months |
| Loyal       | 49–72 Months |

Purpose:

* Capture customer lifecycle stages.
* Improve churn pattern identification.

---

### 2. Service Count

Calculated the total number of active services subscribed by each customer.

Included services:

* Phone Service
* Multiple Lines
* Online Security
* Online Backup
* Device Protection
* Tech Support
* Streaming TV
* Streaming Movies

Purpose:

* Measure customer engagement.
* Assess service adoption levels.

---

### 3. Auto Payment

Created a binary indicator identifying customers using automatic payment methods.

Values:

* 1 → Automatic Payment
* 0 → Manual Payment

Purpose:

* Capture billing behavior patterns associated with retention.

---

### 4. Security Bundle

Created a binary feature identifying customers subscribed to both:

* Online Security
* Tech Support

Purpose:

* Represent customers with enhanced service protection and support coverage.

---

## Data Preprocessing (Current Phase)

The next stage focuses on preparing data for machine learning models.

Planned tasks include:

* Encoding categorical variables
* Handling class imbalance
* Feature scaling (if required)
* Train-test splitting
* Building preprocessing pipelines

---

## Models Planned

The following machine learning models will be evaluated:

* Logistic Regression
* Random Forest Classifier
* LightGBM
* XGBoost

Models will be compared using multiple evaluation metrics to identify the best-performing solution.

---

## Evaluation Metrics

Model performance will be evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC Score
* Confusion Matrix

Special emphasis will be placed on Recall and ROC-AUC due to the business importance of identifying potential churners.

---

## Tools & Technologies

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* LightGBM

### Development Environment

* Google Colab
* Jupyter Notebook

### Version Control

* Git
* GitHub

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

* Business Understanding
* Data Understanding
* Exploratory Data Analysis (EDA)
* Data Cleaning
* Feature Engineering

### In Progress

* Data Preprocessing

### Upcoming

* Model Development
* Model Evaluation
* Hyperparameter Tuning
* Feature Importance Analysis
* Customer Risk Segmentation
* Business Recommendations

---

## Future Enhancements

* Hyperparameter Optimization
* Ensemble Learning Techniques
* Customer Risk Scoring System
* Streamlit Deployment
* Interactive Business Dashboard
* Retention Strategy Recommendation Engine

---

## Author

**Nithin Shibu**

Aspiring Data Analyst | Data Science Enthusiast

Skills:

* Python
* SQL
* Statistics
* Machine Learning
* Data Visualization

This project demonstrates an end-to-end machine learning workflow, from business understanding and exploratory analysis to predictive modeling and business-focused insights.
