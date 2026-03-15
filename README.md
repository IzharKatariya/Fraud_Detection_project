# Fraud Detection Project

## Overview
Machine learning model to detect fraudulent financial transactions 
using XGBoost on a dataset of 6.3 million transactions.

## Dataset
- 6,362,620 rows and 10 columns
- Transaction types: CASH-IN, CASH-OUT, DEBIT, PAYMENT, TRANSFER
- Fraud only occurs in TRANSFER and CASH-OUT transactions

## Features Used
- `step` - Time step (1 hour each)
- `amount` - Transaction amount
- `type_TRANSFER` - Transaction type flag
- `type_CASH_OUT` - Transaction type flag
- `sender_balance_error` - Balance discrepancy (sender)
- `receiver_balance_error` - Balance discrepancy (receiver)

## Model
- **Algorithm:** XGBoost Classifier
- **Handling Imbalance:** scale_pos_weight = 336
- **ROC-AUC Score:** 0.9946
- **Fraud Recall:** 93%

## Libraries
- Pandas, NumPy
- Seaborn, Matplotlib
- Scikit-learn
- XGBoost

## How to Run
1. Clone the repository
2. Install dependencies: `pip install pandas scikit-learn xgboost seaborn matplotlib`
3. Open `Fraud_Detection_Project.ipynb` in Jupyter Notebook
4. Run all cells

## Key Findings
- `sender_balance_error` is the strongest fraud predictor (92% importance)
- Fraudulent transactions drain the sender's account completely
- Fraud only occurs in TRANSFER and CASH-OUT transaction types
