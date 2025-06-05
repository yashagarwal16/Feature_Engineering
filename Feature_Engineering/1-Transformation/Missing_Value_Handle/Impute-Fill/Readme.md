# 🧩 Imputation in Machine Learning

## 📘 What is Imputation?

**Imputation** is the process of **filling in missing values** in a dataset using estimated values, instead of removing or ignoring them.

It helps preserve all data rows and improves the performance of machine learning models.

---

## 🎯 Why Use Imputation?

- Avoid data loss from dropping rows (like in CCA)
- Ensure compatibility with ML models that can't handle NaNs
- Maintain sample size and data integrity

---

## 🧠 Types of Imputation

### 🔹 1. Univariate Imputation

Impute missing values using **only the feature itself**.

#### ✅ Common Strategies:

| Strategy        | Description                                  | Suitable For     |
|----------------|----------------------------------------------|------------------|
| Mean            | Replace with column average                  | Continuous data  |
| Median          | Replace with column median                   | Skewed data      |
| Mode            | Replace with most frequent value             | Categorical data |
| Constant        | Replace with a fixed custom value            | Any type         |

```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy='mean')
df[['Age']] = imputer.fit_transform(df[['Age']])
````

⚠️ Does not consider relationships with other features

---

### 🔸 2. Multivariate Imputation

Impute using **other features** in the dataset.

#### 📌 Methods:

#### 🔹 KNN Imputer

* Finds similar samples (nearest neighbors) to estimate missing values

```python
from sklearn.impute import KNNImputer

imputer = KNNImputer(n_neighbors=3)
df_filled = imputer.fit_transform(df)
```

#### 🔹 Iterative Imputer (MICE)

* Uses regression models to predict missing values iteratively from other columns

```python
from sklearn.impute import IterativeImputer

imputer = IterativeImputer()
df_filled = imputer.fit_transform(df)
```

✅ More accurate
⚠️ Computationally heavier

---

### 🔧 3. Custom/Domain-Based Imputation

* Use **domain knowledge** to fill missing values
* Example: Fill missing "Experience" with 0 if "Student" = True

✅ Very interpretable
⚠️ Needs external insight

---

## 🧮 Summary Table

| Type         | Strategy           | Uses Other Columns? | Suitable For      |
| ------------ | ------------------ | ------------------- | ----------------- |
| Univariate   | Mean, Median, Mode | ❌ No                | Simple imputation |
| Multivariate | KNN, Iterative     | ✅ Yes               | Better accuracy   |
| Custom       | Business Logic     | ⚠️ Maybe            | Domain-specific   |

---

## ✅ When to Use Which?

| Situation                                | Recommended Method       |
| ---------------------------------------- | ------------------------ |
| Few missing values, fast solution needed | Univariate (mean/median) |
| Data relationships are important         | Multivariate (KNN, MICE) |
| You have domain knowledge                | Custom rules             |

---

## 🧪 Checking Missing Values

```python
df.isnull().sum()
```

---

## 📌 Final Tips

* Always explore **why** data is missing
* Use a **copy of the dataset** to test different imputation strategies
* Compare model performance **before and after** imputation
