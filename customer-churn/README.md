# Customer Churn Prediction

Exploratory data analysis and supervised classification on the IBM Telco Customer Churn dataset.

## Goals
- Identify patterns and trends in customer behaviour
- Understand which services and demographics correlate with higher churn
- Build and evaluate classification models to predict churn

## Dataset
- **File:** [`data/Customer_Churn.xlsx`](data/Customer_Churn.xlsx)
- **Source:** IBM Telco Customer Churn
- **Rows:** ~7,043 customers
- **Target:** `Churn` (Yes / No)
- **Features:** demographics (gender, senior citizen, partner, dependents), account info (tenure, contract, payment method, charges) and services (phone, internet, streaming, security, support).

## Workflow
1. **Data loading & cleaning** — convert `TotalCharges` to numeric, drop rows with missing values, drop `customerID`.
2. **Exploratory data analysis** — distributions and churn breakdowns for monthly charges, tenure, contract type, internet service, streaming, etc.
3. **Correlation analysis** — heatmap on numeric features after binarising the target.
4. **Feature engineering** — label-encode binary categoricals, one-hot encode multi-class categoricals, standard-scale numeric columns.
5. **Modelling** — train/test split (80/20) and benchmark five classifiers with `GridSearchCV` (5-fold CV):
   - Logistic Regression
   - SVM
   - Decision Tree
   - Random Forest
   - K-Nearest Neighbours
6. **Evaluation** — accuracy, precision, recall, F1, and confusion matrices. Results written to `model_results.txt`.

## Run

```bash
pip install -r ../requirements.txt
jupyter notebook notebooks/customer_churn.ipynb
```

The notebook reads the dataset from `../data/Customer_Churn.xlsx` (relative to the notebook), so run it from the `notebooks/` directory or via Jupyter.
