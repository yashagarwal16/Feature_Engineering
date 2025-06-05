# 🔄 Multivariate Imputation in Machine Learning

## 📘 What is Multivariate Imputation?

**Multivariate Imputation** fills in missing values by using **multiple features (columns)** to predict the missing values of another.  
Unlike univariate imputation (which only uses one column), this method captures **relationships between features**.

---

## 🎯 Why Use Multivariate Imputation?

- Preserves the correlation between features
- Gives more accurate estimates
- Works well when multiple variables have missing values

---

## 🔍 Popular Techniques

### 🔹 1. KNN Imputation (K-Nearest Neighbors)

- Finds the `k` nearest rows (neighbors) that are **most similar**
- Uses them to compute the missing value (e.g., by average)

```python
from sklearn.impute import KNNImputer

imputer = KNNImputer(n_neighbors=3)
df_filled = imputer.fit_transform(df)
````

✅ Good for numeric data
⚠️ Sensitive to scale (use standardization before)

---

### 🔸 2. Iterative Imputer (MICE)

* **MICE** = *Multiple Imputation by Chained Equations*
* Predicts missing values of one feature using a **regression model** built on the others
* Repeats the process **iteratively** for all features

```python
from sklearn.impute import IterativeImputer

imputer = IterativeImputer()
df_filled = imputer.fit_transform(df)
```

✅ Very powerful and flexible
⚠️ Computationally intensive

---

## 🧮 Summary Comparison

| Method                | Based On         | Best For              | Limitations                              |
| --------------------- | ---------------- | --------------------- | ---------------------------------------- |
| **KNN Imputer**       | Similar Rows     | Small to medium data  | Affected by outliers, slow on large data |
| **Iterative Imputer** | Feature Modeling | Complex relationships | Requires more compute resources          |

---

## ✅ When to Use Multivariate Imputation?

* When **more than one feature** has missing values
* When there is a **strong correlation** between features
* When dataset is **not too large** (to avoid long training time)

---

## ⚠️ When NOT to Use

* Very sparse or extremely large datasets
* No strong relationships between features
* Need for quick and simple preprocessing (use univariate instead)

---

## 🧪 Tip: Always Standardize Before KNN

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
df_scaled = scaler.fit_transform(df)

imputer = KNNImputer()
df_imputed = imputer.fit_transform(df_scaled)
```

---

## 📌 Final Thoughts

Multivariate imputation is one of the **most accurate ways** to handle missing data, especially when:

* The dataset is rich
* Features are interrelated
* Precision matters