# 🧠 Telco Customer Churn Prediction (Random Forest)

## 📋 Project Overview

Customer churn — when users stop using a company's services — is a major problem in the telecommunications industry. Predicting which customers are likely to churn helps companies take proactive actions to retain them.

This project uses **Random Forest Classification** to predict customer churn based on the Telco Customer Churn dataset.
--
## Objectives

- Analyze customer behavior patterns
- Build a predictive model to identify at-risk customers
- Provide actionable insights for customer retention strategies
  
## Dataset
**Source:** [Kaggle - Telco Customer Churn](https://www.kaggle.com/blastchar/telco-customer-churn)

**Description:**  
This dataset contains information about a telecommunication company’s customers, including their demographic details, subscribed services, contract types, and billing methods. The target variable is **`Churn`**, which indicates whether a customer has discontinued the service.

**Dataset Details:**
- **Records:** ~7,000 customers  
- **Target Variable:** `Churn` (Yes / No)

**Feature Categories:**
| Category | Example Features |
|-----------|------------------|
| 🧍‍♂️ **Demographics** | gender, SeniorCitizen, Partner, Dependents |
| 🌐 **Services** | InternetService, OnlineSecurity, StreamingTV |
| 💳 **Billing & Payments** | MonthlyCharges, TotalCharges, PaymentMethod |
| 📄 **Contracts** | Contract type, tenure |

## Workflow

### 1. Data Preprocessing
* Converted `TotalCharges` from `object` → `float`
* Handled missing values and categorical encoding with `OneHotEncoder`
* Scaled numerical features using `StandardScaler`
* Split dataset into training (80%) and testing (20%)

### 2. Modeling
* Built a pipeline combining preprocessing and a RandomForestClassifier
* Used `class_weight='balanced'` to handle class imbalance

### 3. Hyperparameter Tuning
* Used `RandomizedSearchCV` with 5-fold cross-validation
* Tuned parameters like:
  * `n_estimators`, `max_depth`, `min_samples_split`, `max_features`

## Model Performance
---

| Metric            | Value |
| :---------------- | :---- |
| Accuracy          | 0.79  |
| ROC-AUC           | 0.83  |
| Precision (Churn) | 0.65  |
| Recall (Churn)    | 0.47  |
| F1-score (Churn)  | 0.54  |

---
| Metric            | Value    |
| :---------------- | :------- |
| Accuracy          | **0.81** |
| ROC-AUC           | **0.86** |
| Precision (Churn) | **0.69** |
| Recall (Churn)    | **0.52** |
| F1-score (Churn)  | **0.59** |

✅ Improved ROC-AUC and recall show the tuned model identifies more churners effectively.

### Insights & Recommendations
- Short-term contract users are most likely to churn — promote longer-term plans.
- High monthly charges correlate with churn — offer targeted discounts or bundles.
- Low tenure customers may need onboarding or loyalty incentives.

### Tech Used
- Python
- Pandas, NumPy, Matplotlib, Seaborn
- Scikit-learn (Pipelines, RandomForest, RandomizedSearchCV)
- Jupyter Notebook
