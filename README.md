# 📊 Telco Customer Churn Prediction

A machine learning project that predicts customer churn using the Telco Customer Churn dataset. The project focuses on building a production-style Scikit-Learn pipeline, preventing data leakage, evaluating against a baseline model, and measuring the impact of feature engineering.

---

## 🎯 Project Objective

Customer churn is one of the most important business problems in the telecom industry. Retaining existing customers is often more cost-effective than acquiring new ones.

The objective of this project is to:

- Predict whether a customer is likely to churn.
- Build a leakage-free machine learning workflow.
- Compare model performance against a simple baseline.
- Evaluate the impact of engineered features.
- Follow industry-standard ML practices using Scikit-Learn Pipelines and Cross-Validation.

---

## 📂 Dataset

**Dataset:** Telco Customer Churn Dataset

**Target Variable:**

- `Churn`
  - Yes = Customer left the company
  - No = Customer stayed

### Feature Categories

- Customer Demographics
- Subscription Services
- Internet Services
- Contract Information
- Billing & Payment Information

---

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Scikit-Learn
- Jupyter Notebook
- Git & GitHub

---

## 🔄 Project Workflow

### 1. Data Loading

- Imported and inspected the dataset.
- Checked data types and missing values.

### 2. Train-Test Split

- Data was split before any preprocessing.
- Prevented information leakage from the test set.

### 3. Baseline Model

A simple baseline was created before training any machine learning model.

**Baseline Accuracy:** `73.46%`

This score became the minimum benchmark that every subsequent model had to beat.

### 4. Data Preprocessing Pipeline

Implemented a complete Scikit-Learn Pipeline containing:

- Missing value imputation
- One-hot encoding
- Feature transformations
- Logistic Regression model

All preprocessing steps were performed inside the pipeline to avoid leakage.

### 5. Cross Validation

Applied Stratified Cross Validation to obtain a more reliable estimate of model performance.

**Mean CV Accuracy:** `80.33%`

### 6. Feature Engineering

Created and evaluated custom business-oriented features.

---

## 🚀 Engineered Features

### 1. AvgMonthlySpend

```python
TotalCharges / tenure
```

Represents average customer spending per month.

**Impact:**

```
80.34% → 80.41%
(+0.07%)
```

---

### 2. IsLongTermCustomer

```python
1 if tenure >= 12 else 0
```

Identifies long-term customers.

**Impact:**

```
80.41% → 80.70%
(+0.29%)
```

⭐ Highest impact feature

---

### 3. HighMonthlyChargeCustomer

```python
1 if MonthlyCharges >= 90 else 0
```

Identifies customers with high monthly bills.

**Impact:**

```
80.70% → 80.77%
(+0.07%)
```

---

## 📈 Model Performance

| Model Version | Accuracy |
|--------------|----------:|
| Baseline Model | 73.46% |
| Initial Pipeline | 80.34% |
| + AvgMonthlySpend | 80.41% |
| + IsLongTermCustomer | 80.70% |
| + HighMonthlyChargeCustomer | **80.77%** |

### Final Improvement

```text
Final Model Accuracy : 80.77%
Baseline Accuracy    : 73.46%

Improvement          : +7.31 percentage points
```

---

## 🔒 Data Leakage Prevention

Data leakage was actively prevented by:

- Splitting data before preprocessing.
- Performing imputation inside the pipeline.
- Performing encoding inside the pipeline.
- Avoiding target-derived features.
- Using cross-validation correctly.

Detailed explanation:

➡️ See `LEAKAGE.md`

---

## 📁 Project Structure

```text
crunchy-data-scientist-t1-rudra_ya_10/
│
├── data/
│   └── raw/
│
├── notebooks/
│   └── baseline_to_model.ipynb
│
├── LEAKAGE.md
├── README.md
├── requirements.txt
│
└── .gitignore
```

---

## 🎓 Key Learning Outcomes

Through this project I learned:

- Machine Learning Workflow Design
- Data Leakage Prevention
- Scikit-Learn Pipelines
- Cross Validation
- Feature Engineering
- Model Evaluation
- Git & GitHub Version Control

---

## 👨‍💻 Author

**Rudra Pratap Singh**

B.Tech Computer Science (Minor in Data Analytics)

Aspiring Data Analyst | SQL | Power BI | Python | Machine Learning

GitHub: https://github.com/RudraPratapSingh10