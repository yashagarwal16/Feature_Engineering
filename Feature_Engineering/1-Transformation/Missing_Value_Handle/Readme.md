# ❓ Handling Missing Values in Machine Learning

## 📘 What Are Missing Values?

**Missing values** occur when no data value is stored for a variable in an observation.  
They can negatively affect model training and predictions if not handled properly.

---

## 🔍 Why Handle Missing Values?

- Many ML algorithms **cannot handle missing data**
- Unhandled missing values can **bias results** or **reduce accuracy**
- Proper handling ensures **data quality and model reliability**

---

## 🧰 Techniques to Handle Missing Data

We can categorize the techniques into:

1. 🔸 **Remove the Data**
2. 🔸 **Impute (Fill in) the Data**
3. 🔸 **Use Specialized Models**

---

## 🔴 1. Removal (Listwise or CCA)

### 📌 Complete Case Analysis (CCA) or Listwise Deletion
- Remove rows where **any value is missing**

✅ Easy and quick  
⚠️ Risky if too many rows are lost  
⚠️ Assumes missingness is **completely random**

```python
df.dropna(inplace=True)  # removes all rows with any NaN
````

---

## 🟡 2. Imputation (Filling Missing Values)

Imputation means replacing missing values with estimated ones.

### 📘 Types of Imputation

---

### 📌 a. **Univariate Imputation**

Only uses the **feature with missing data** to fill it.

#### 🔹 Common Strategies:

* Mean
* Median
* Mode (for categorical)
* Constant value

```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy='mean')  # or 'median', 'most_frequent', 'constant'
df[['age']] = imputer.fit_transform(df[['age']])
```

✅ Fast and easy
⚠️ May ignore relationships between features

---

### 📌 b. **Multivariate Imputation**

Uses **other features** to predict missing values using a model.

#### 🔹 Example Methods:

* **KNN Imputer**
* **Iterative Imputer** (like MICE – Multiple Imputation by Chained Equations)

```python
from sklearn.impute import KNNImputer, IterativeImputer

knn_imputer = KNNImputer(n_neighbors=3)
df_filled = knn_imputer.fit_transform(df)

iter_imputer = IterativeImputer()
df_filled_iter = iter_imputer.fit_transform(df)
```

✅ More accurate
⚠️ Slower and complex

---

## 🟢 3. Custom/Domain-Specific Imputation

* Fill missing values using **business rules** or **external sources**
* Example: Fill missing "Salary" with industry average by job role

✅ Realistic in domain-specific settings
⚠️ Requires domain expertise

---

## 🧮 Summary Table

| Method            | Type            | Pros                       | Cons                          |
| ----------------- | --------------- | -------------------------- | ----------------------------- |
| Remove Rows (CCA) | Removal         | Simple, fast               | Data loss, biased model       |
| Mean/Median/Mode  | Univariate      | Easy, quick                | Ignores feature relationships |
| KNN Imputer       | Multivariate    | Considers feature patterns | Computational cost            |
| Iterative Imputer | Multivariate    | Most accurate, flexible    | Complex, slower               |
| Custom Rules      | Domain-Specific | Accurate with expertise    | Needs external knowledge      |

---

## ✅ When to Use What?

| Situation                                               | Recommended Method                   |
| ------------------------------------------------------- | ------------------------------------ |
| Few missing values                                      | Remove or Mean/Median                |
| Data is MCAR (Missing Completely At Random)             | Any method works                     |
| Data is MAR (Missing At Random) or MNAR (Not at Random) | Prefer Multivariate                  |
| Categorical feature                                     | Mode or Custom Label                 |
| Time-series data                                        | Forward/Backward Fill, Interpolation |

---

## 🧪 Bonus: Check Missing Values in Pandas

```python
df.isnull().sum()
```

---

## 📌 Final Tip

Never ignore missing data — handle it **before training your model** for reliable and accurate results.
