# 🧹 CCA (Complete Case Analysis)

## 📘 What is CCA?

**CCA (Complete Case Analysis)**, also known as **Listwise Deletion**, is a method used to handle missing data by **removing entire rows** that contain **any missing values**.

---

## 🧠 How It Works

If a row has **even one missing value**, the entire row is **dropped** from the dataset.

### 🔍 Example

| Age | Salary | City     |
|-----|--------|----------|
| 25  | 50000  | Delhi    |
| NaN | 60000  | Mumbai   |
| 30  | NaN    | Kolkata  |
| 40  | 70000  | Chennai  |

🔻 After applying **CCA**:

| Age | Salary | City   |
|-----|--------|--------|
| 25  | 50000  | Delhi  |
| 40  | 70000  | Chennai|

---

## ✅ Advantages

- Simple and easy to apply
- Keeps only complete, clean data
- Maintains consistency across features

---

## ❌ Disadvantages

- **Data loss**: Removes potentially useful data
- Can **bias** the dataset if missing values are not random
- Not recommended when a large portion of the data is missing

---

## 🧪 Python Example

```python
import pandas as pd

# Drop all rows with any missing values
df_clean = df.dropna()
````

---

## 📌 When to Use CCA

| Condition                             | Use CCA? |
| ------------------------------------- | -------- |
| Very few missing values               | ✅ Yes    |
| Large dataset, small missing rate     | ✅ Yes    |
| Many missing values per row           | ❌ No     |
| Data not missing completely at random | ❌ No     |

---

## 🔄 Alternative Methods

If CCA removes too much data, consider:

* Mean/Median Imputation
* KNN or Iterative Imputation
* Custom Domain Rules
