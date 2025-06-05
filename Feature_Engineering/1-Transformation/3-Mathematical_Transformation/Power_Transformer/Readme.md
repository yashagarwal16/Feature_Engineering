# ⚡ Power Transformation in Machine Learning

## 📘 What is Power Transformation?

**Power Transformation** is a technique used to make skewed data more **normal (bell-shaped)** by applying mathematical functions.  
It helps machine learning models that perform better with **normally distributed** features.

---

## 🎯 Why Use Power Transformation?

- To **reduce skewness** in the data
- To **normalize** feature distributions
- To help algorithms like **Linear Regression**, **Logistic Regression**, and **SVM** perform better
- To **stabilize variance**

---

## 🔧 Types of Power Transformations

### 📌 1. Box-Cox Transformation
- Works **only for positive data**
- Automatically finds the best transformation (lambda `λ`)
- Formula:
```

f(x) = (x^λ - 1) / λ, if λ ≠ 0
log(x),          if λ = 0

```

### 📌 2. Yeo-Johnson Transformation
- Works with **positive, zero, and negative values**
- Similar to Box-Cox but more flexible
- Also learns the best λ to make data close to normal

---

## 📊 Visual Example

### Original Skewed Data

```

```
 *
 *
**
**
```

---

---

---

```

### After Power Transformation (More Normal)

```

```
  ***
******
```

---

---

---

```
******
  ***
```

````

---

## 🧪 Python Code Example

```python
from sklearn.preprocessing import PowerTransformer

# Using Yeo-Johnson (default)
pt = PowerTransformer(method='yeo-johnson')
transformed_data = pt.fit_transform(data)

# Optional: Box-Cox for positive-only data
pt_boxcox = PowerTransformer(method='box-cox')
transformed_data = pt_boxcox.fit_transform(positive_data)
````

---

## ✅ Summary Table

| Transformation | Supports Negatives | Learns Best λ | Use When        |
| -------------- | ------------------ | ------------- | --------------- |
| Box-Cox        | ❌ No               | ✅ Yes         | Data > 0        |
| Yeo-Johnson    | ✅ Yes              | ✅ Yes         | Data may be ≤ 0 |

---

## 📌 When to Use

* Your data is **heavily skewed**
* You want to **normalize** numeric features
* Your model **assumes normal distribution** or performs poorly on raw data

---

## 📁 Use in ML Projects

Power transformation can be a **key part of preprocessing pipelines** to improve:

* Model accuracy
* Training speed
* Feature scaling quality

---

```