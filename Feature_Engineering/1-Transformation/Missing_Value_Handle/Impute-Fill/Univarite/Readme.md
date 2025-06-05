# 🔧 Univariate Imputation in Machine Learning

## 📘 What is Univariate Imputation?

**Univariate Imputation** is a simple technique to handle missing data by replacing missing values in a column using **only the values from that same column** (i.e., no other columns are used).

---

## 🎯 Why Use Univariate Imputation?

- Very simple and fast
- Keeps dataset size the same
- Good baseline for missing value handling

---

## 🧠 Common Strategies

| Strategy        | Description                                  | Suitable For     |
|----------------|----------------------------------------------|------------------|
| **Mean**        | Replaces missing values with the column average  | Continuous data  |
| **Median**      | Replaces missing values with the column median  | Skewed data      |
| **Mode**        | Replaces missing values with the most frequent value | Categorical data |
| **Constant**    | Replaces missing values with a fixed value      | Any type         |

---

## 🔍 Example

| Age | Salary |
|-----|--------|
| 25  | 50000  |
| NaN | 60000  |
| 30  | NaN    |
| 40  | 70000  |

### ➤ Imputation (Mean of Age = 31.6)

| Age  | Salary |
|------|--------|
| 25   | 50000  |
| 31.6 | 60000  |
| 30   | 60000  |
| 40   | 70000  |

---

## 🧪 Python Example

```python
from sklearn.impute import SimpleImputer

# For numerical features
imputer = SimpleImputer(strategy='mean')
df[['Age']] = imputer.fit_transform(df[['Age']])

# For categorical features
cat_imputer = SimpleImputer(strategy='most_frequent')
df[['City']] = cat_imputer.fit_transform(df[['City']])
````

---

## ✅ When to Use

| Condition                                | Use Univariate? |
| ---------------------------------------- | --------------- |
| Few missing values                       | ✅ Yes           |
| Fast preprocessing needed                | ✅ Yes           |
| No strong correlation with other columns | ✅ Yes           |

---

## ❌ Limitations

* **Ignores relationships** with other features
* May introduce **bias** if data is not missing at random
* Not ideal for **large gaps or complex data**

---

## 📌 Tip

Univariate imputation is great for:

* Quick EDA
* Baseline models
* Early stages of data cleaning