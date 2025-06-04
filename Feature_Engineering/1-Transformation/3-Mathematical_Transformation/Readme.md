# 🔢 Mathematical Transformations in Machine Learning

## 🧠 What is a Mathematical Transformation?

A **mathematical transformation** is a technique used to **modify feature values** to improve the performance of a machine learning model.

Transformations are typically used to:
- Reduce **skewness**
- Handle **non-linear relationships**
- Stabilize **variance**
- Make data more **normally distributed**

---

## ⚙️ Why Do We Use Mathematical Transformations?

- Many algorithms (like **Linear Regression**, **Logistic Regression**) assume **normally distributed** or **linear data**
- Helps models learn **better patterns and relationships**
- Makes feature values more **suitable for model training**

---

## 🛠️ Types of Mathematical Transformations

### 1. 🔹 Log Transformation

**Formula:**

```

x' = log(x)

```

**Use When:**
- Data is **positively skewed**
- Large values dominate small values

**Note:** Input must be **positive**

---

### 2. 🔹 Square Root Transformation

**Formula:**

```

x' = √x

```

**Use When:**
- Reducing impact of **large values**
- Making skewed data more **symmetric**

**Note:** Input must be **non-negative**

---

### 3. 🔹 Reciprocal Transformation

**Formula:**

```

x' = 1 / x

```

**Use When:**
- Handling **large outliers**
- Making big numbers small

**Note:** Cannot be applied to **0 or negative values**

---

### 4. 🔹 Box-Cox Transformation

**Use When:**
- You want to **automatically find the best transformation** to make data normal

**Note:** Only works for **positive values**

---

### 5. 🔹 Yeo-Johnson Transformation

**Use When:**
- Like Box-Cox, but works for **zero and negative values** too

---

### 6. 🔹 Power Transformation

**Formula:**

```

x' = xⁿ (e.g., x², x⁰·⁵)

```

**Use When:**
- You want to **adjust data distribution**
- Often used in **feature engineering**

---

### 7. 🔹 Z-score Normalization (Standardization)

**Formula:**

```

z = (x - mean) / std

```

**Use When:**
- Centering data around **mean = 0**
- Making **variance = 1**

---

## ✅ Summary Table

| Transformation      | Purpose                              | Handles Negatives? |
|---------------------|--------------------------------------|---------------------|
| Log                 | Reduce skew, compress large values   | ❌ No               |
| Square Root         | Reduce skew, moderate compression    | ❌ No               |
| Reciprocal          | Reduce impact of large outliers      | ❌ No (Not zero)    |
| Box-Cox             | Normalize data (auto λ)              | ❌ No               |
| Yeo-Johnson         | Normalize data with negatives        | ✅ Yes              |
| Power Transform     | Adjust shape (e.g., square, cube)    | ❌ Usually No       |
| Z-score             | Center & scale data                  | ✅ Yes              |

---

## 🧑‍🏫 When to Use Mathematical Transformations?

- When data is **not normally distributed**
- When there are **strong outliers or skewness**
- When models assume **linear relationships** or **equal variance**
```