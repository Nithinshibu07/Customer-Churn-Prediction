# Customer Churn Prediction

A machine learning project that predicts whether a telecom customer is likely to churn, using the Telco Customer Churn dataset. The pipeline covers end-to-end data processing, feature engineering, model training, hyperparameter tuning, and deployment-ready model saving.

---

## Project Overview

Customer churn is one of the most critical business problems in the telecom industry. This project builds a binary classification model to identify at-risk customers so that retention strategies can be applied proactively.

**Dataset:** [Telco Customer Churn](https://raw.githubusercontent.com/Nithinshibu07/Customer-Churn-Prediction/main/data/raw/Telco_customer_churn.xlsx)  
**Target Variable:** `Churn Label` (Yes / No → 1 / 0)  
**Final Model:** Random Forest Classifier (selected by F1 Score)

---

## Solution Approach

### 1. Exploratory Data Analysis (EDA)
- Analysed churn distribution (~26.5% churn rate — imbalanced dataset)
- Identified key patterns:
  - Customers with **lower tenure** churn more
  - **Higher monthly charges** correlate with higher churn
  - **Month-to-month contracts** have the highest churn rates
  - **Fiber optic** internet users churn more than DSL or no-internet users

### 2. Data Cleaning
- Converted `Total Charges` from object to numeric (coerced errors to 0)
- Dropped irrelevant or leakage columns: `CustomerID`, `Churn Score`, `CLTV`, `Churn Reason`, location fields

### 3. Feature Engineering
| Feature | Description |
|---|---|
| `Tenure Group` | Customer lifecycle stage: New / Growing / Established / Loyal |
| `Service Count` | Number of services the customer subscribes to |
| `Auto Payment` | Whether the customer uses automatic payment (1/0) |

### 4. Preprocessing
- Replaced `"No internet service"` / `"No phone service"` with `"No"` for consistency
- One-hot encoding for all categorical features
- `StandardScaler` applied to numerical columns: `Tenure Months`, `Monthly Charges`, `Total Charges`, `Service Count`
- Stratified 80/20 train-test split

### 5. Handling Class Imbalance
- Applied **SMOTE** (Synthetic Minority Oversampling Technique) on the training set
- Post-SMOTE training set: 4,139 churned + 4,139 non-churned

### 6. Model Training & Selection
- Evaluated **Random Forest** and **LightGBM** using 5-fold Stratified Cross Validation (ROC-AUC)
- Applied `RandomizedSearchCV` for hyperparameter tuning on both models
- **Random Forest selected** as the final model based on F1 Score

### 7. Final Model Performance

| Metric | Score |
|---|---|
| Accuracy | 77.6% |
| Precision | 56.9% |
| Recall | 65.2% |
| F1 Score | 60.8% |
| ROC-AUC | 82.98% |

### 8. Top Churn Drivers (Feature Importance)
1. Tenure Months
2. Total Charges
3. Monthly Charges
4. Dependents
5. Contract Type

---

## Repository Structure

```
Customer-Churn-Prediction/
│
|── notebooks/
│   └── Customer_churn_prediction.ipynb
|       └── .gitkeep
├── data/
│   ├── raw/
│   │   └── Telco_customer_churn.xlsx
│   │
│   └── Processed_Data/
|       └── churn_processed.csv
│       └── .gitkeep
│
├── models/
│   └── customer_churn_model.pkl
│       └── .gitkeep
|
├── report/
│   └── plots/
│       ├── CLTV vs Churn.png
│       ├── Churn Percentage.png
│       ├── Contract Type vs Churn Rate %.png
│       ├── Correlation Matrix.png
│       ├── Customer Churn Distribution.png
│       ├── Distribution of Monthly Charges.png
│       ├── Distribution of Tenure Months.png
│       ├── Internet Service vs Churn Rate %.png
│       ├── Monthly Charges vs Churn.png
│       └── Tenure vs Churn.png
│
│
├── .gitignore
├── README.md
└── requirements.txt

```

---

## Prerequisites

- Python 3.8+
- pip

---

## Setup & Installation

**1. Clone the repository**

```bash
git clone https://github.com/Nithinshibu07/Customer-Churn-Prediction.git
cd Customer-Churn-Prediction
```

**2. Create and activate a virtual environment (recommended)**

```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

---

## Dependencies

```
pandas
numpy
matplotlib
seaborn
scikit-learn
lightgbm
imbalanced-learn
openpyxl
pickle-mixin
```

Install all at once:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn lightgbm imbalanced-learn openpyxl
```

---

## Usage

### Run the full notebook

Open and run all cells in `notebooks/customer_churn_prediction.ipynb` using Jupyter:

```bash
jupyter notebook notebooks/customer_churn_prediction.ipynb
```

### Predict churn for a new customer

After running the notebook (which saves the model), you can load and use it directly:

```python
import pickle
import pandas as pd

# Load the saved model
with open("models/customer_churn_model.pkl", "rb") as f:
    model_data = pickle.load(f)

loaded_model = model_data["model"]
scaler = model_data["scaler"]
feature_names = model_data["feature_names"]

# Define a new customer
input_data = {
    "Gender": "Male",
    "Senior Citizen": "No",
    "Partner": "No",
    "Dependents": "No",
    "Tenure Months": 1,
    "Phone Service": "Yes",
    "Multiple Lines": "Yes",
    "Internet Service": "Fiber optic",
    "Online Security": "No",
    "Online Backup": "No",
    "Device Protection": "No",
    "Tech Support": "No",
    "Streaming TV": "Yes",
    "Streaming Movies": "Yes",
    "Contract": "Month-to-month",
    "Paperless Billing": "Yes",
    "Payment Method": "Electronic check",
    "Monthly Charges": 115.50,
    "Total Charges": 115.50
}

# Run prediction (use the prepare_new_customer function from the notebook)
new_customer = pd.DataFrame([input_data])
new_customer = prepare_new_customer(new_customer)

prediction = loaded_model.predict(new_customer)
probability = loaded_model.predict_proba(new_customer)[:, 1]

print("Prediction:", "Churn" if prediction[0] == 1 else "Stay")
print("Churn Probability:", round(probability[0] * 100, 2), "%")
```

---

## .gitignore

```
# Python
__pycache__/
*.py[cod]
*.pyo
.env
venv/
.venv/

# Jupyter
.ipynb_checkpoints/

# Model artifacts (optional — include if you want to version the model)
# *.pkl

# OS
.DS_Store
Thumbs.db

# Build
dist/
build/
*.egg-info/
```


---

## License

This project is for educational purposes.
