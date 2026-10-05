# Telco Customer Churn Prediction

## Project Overview

This project predicts customer churn using the Telco Customer Churn dataset.

The goal is to build a machine learning pipeline while preventing data leakage and comparing model performance against a simple baseline.

---

## Dataset

Telco Customer Churn Dataset

Target Variable:
- Churn

Features:
- Customer demographics
- Service subscriptions
- Billing information
- Contract details

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook
- Git

---

## Workflow

1. Train-Test Split
2. Baseline Model
3. Data Preprocessing Pipeline
4. Cross Validation
5. Feature Engineering
6. Model Evaluation

---

## Engineered Features

### 1. AvgMonthlySpend

TotalCharges / tenure

Measures average spending per month.

### 2. IsLongTermCustomer

1 if tenure >= 12 else 0

Identifies long-term customers.

### 3. HighMonthlyChargeCustomer

1 if MonthlyCharges >= 90 else 0

Identifies high-paying customers.

---

## Results

| Model | Accuracy |
|---------|---------:|
| Baseline Model | 73.46% |
| Original Pipeline | 80.34% |
| + AvgMonthlySpend | 80.41% |
| + IsLongTermCustomer | 80.70% |
| + HighMonthlyChargeCustomer | 80.77% |

Final Improvement Over Baseline:

80.77% - 73.46% = 7.31 percentage points

---

## Leakage Prevention

See LEAKAGE.md

---

## Project Structure

data/
notebooks/
requirements.txt
README.md
LEAKAGE.md

---

## Author

Rudra Pratap Singh