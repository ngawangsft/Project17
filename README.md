# Customer Churn Prediction — Telecom Operator (Interconnect)

## Project Overview
Interconnect, a telecom operator, aims to predict customer churn so that at-risk clients can be proactively offered promotional incentives and tailored service plans.  
This project focuses on exploratory data analysis, feature engineering, and machine learning modeling to accurately identify customers likely to churn.

The primary evaluation metric is **AUC-ROC**, chosen due to class imbalance in the target variable.

---

## Business Problem
Customer churn has a direct impact on revenue and customer lifetime value.  
By predicting churn in advance, Interconnect’s marketing team can prioritize retention strategies for high-risk customers.

---

## Data Description
The dataset consists of information for **7,043 customers**, collected from multiple sources and merged using a unique customer identifier (`customerID`).

**Data files included:**
- `contract.csv` — contract details and payment information  
- `personal.csv` — customer demographic information  
- `internet.csv` — internet service usage  
- `phone.csv` — telephone service usage  

**Target variable:**  
- A customer is considered churned if `EndDate` ≠ `"No"`

**Data validity:**  
- Contract information is current as of **February 1, 2020**

---

## Project Structure
├── Part_1_Data_Preprocessing.ipynb
├── Part_2_Modeling_and_Evaluation.ipynb
├── contract.csv
├── personal.csv
├── internet.csv
├── phone.csv
└── README.md

---

## Methodology

### Part 1 — Data Preprocessing & EDA
- Merged multiple datasets into a single analytical table
- Cleaned and standardized categorical and numerical features
- Handled missing values and inconsistencies
- Performed exploratory data analysis to understand churn patterns
- Engineered new features to better capture customer behavior

### Part 2 — Modeling & Evaluation
- Train/validation/test split with stratification on the churn target
- Baseline model: Logistic Regression
- Advanced models:
  - Gradient Boosting
  - LightGBM
  - XGBoost
- Hyperparameter tuning using:
  - Randomized Search
  - Grid Search
- Model evaluation using:
  - AUC-ROC (primary)
  - Accuracy, Precision, Recall, F1
  - ROC curves and confusion matrices
- Threshold tuning for recall vs precision trade-offs

---

## Final Model Performance
**Final Model:** XGBoost (Grid Search optimized)

- **Validation AUC:** 0.85294  
- **Test AUC:** 0.8563  

XGBoost demonstrated the largest improvement over baseline models and provided the best balance of performance and stability.

---

## Key Insights
- Feature engineering significantly improved model performance
- Contract type, payment method, service usage, and cost-based features were strong churn indicators
- Threshold tuning allows flexibility depending on business priorities (higher recall vs balanced precision)
- Ensemble approaches were tested but provided negligible improvement over a single optimized XGBoost model

---

## Reproducibility
- All notebooks contain executed cells with visible outputs
- All datasets used in the analysis are included in the repository
- No additional setup is required to review results

---

## Conclusion
This project demonstrates a structured machine learning workflow for churn prediction, from data preprocessing and feature engineering to model optimization and evaluation.  
The final model provides actionable insights that can support targeted customer retention strategies.