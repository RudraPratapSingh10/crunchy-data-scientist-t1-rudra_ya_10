# LEAKAGE.md

## Data Leakage Prevention

### 1. Train-Test Split Before Preprocessing

Potential Leakage:
If preprocessing is performed on the entire dataset before splitting, information from the test set can leak into the training process.

Prevention:
The dataset was split into training and testing sets before any preprocessing or model training.

---

### 2. Missing Value Imputation Inside Pipeline

Potential Leakage:
Calculating imputation statistics (such as median or most frequent values) on the full dataset would expose information from the test set.

Prevention:
All imputations were performed inside an sklearn Pipeline using SimpleImputer. The imputer was fitted only on the training folds during training and cross-validation.

---

### 3. Feature Engineering Without Target Information

Potential Leakage:
Features derived directly or indirectly from the target variable (Churn) can leak future information into the model.

Prevention:
All engineered features were created only from input variables:

- AvgMonthlySpend = TotalCharges / tenure
- IsLongTermCustomer = tenure >= 12
- HighMonthlyChargeCustomer = MonthlyCharges >= 90

No feature used information from the target variable.

---

## Summary

The project prevents data leakage by:

1. Splitting data before preprocessing.
2. Performing preprocessing inside sklearn Pipelines.
3. Avoiding target-derived features.

This ensures that model evaluation reflects real-world performance.