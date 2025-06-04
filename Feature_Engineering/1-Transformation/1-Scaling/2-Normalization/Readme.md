# 📏 Feature Scaling: Normalization in Machine Learning

## 🔍 What is Normalization?

**Normalization** is a data preprocessing technique used to **rescale feature values** so they are on a similar scale.

This is important because many machine learning algorithms perform better or converge faster when input features are scaled.

---

## ⚙️ 1. Min-Max Normalization

### ✅ Formula:

```
x_scaled = (x - min(x)) / (max(x) - min(x))
```

- Scales features to a **range [0, 1]**
- Preserves relationships between values
- ⚠️ **Sensitive to outliers**

### 🧪 Python Example (Using scikit-learn):

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
scaled_data = scaler.fit_transform(data)
```

---

## ⚙️ 2. Standardization (Z-score Scaling)

### ✅ Formula:

```
z = (x - mean) / standard_deviation
```

- Centers features around **0**
- Scales to **unit variance (1)**
- Suitable when data is **normally distributed**

### 🧪 Python Example:

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaled_data = scaler.fit_transform(data)
```

---

## ⚙️ 3. MaxAbs Scaling

### ✅ Formula:

```
x_scaled = x / max(abs(x))
```

- Scales to range **[-1, 1]**
- Good for **sparse data** (many zeros)
- Keeps sign of data

### 🧪 Python Example:

```python
from sklearn.preprocessing import MaxAbsScaler

scaler = MaxAbsScaler()
scaled_data = scaler.fit_transform(data)
```

---

## ⚙️ 4. Robust Scaling

### ✅ Formula:

```
x_scaled = (x - median) / IQR
```

- Uses **median** and **interquartile range**
- **Robust to outliers**

### 🧪 Python Example:

```python
from sklearn.preprocessing import RobustScaler

scaler = RobustScaler()
scaled_data = scaler.fit_transform(data)
```

---

## 🧭 When to Use Which?

| Method             | Best Use Case                                                              |
|--------------------|----------------------------------------------------------------------------|
| **Min-Max**        | When you need data in a **fixed range [0, 1]**, such as for neural networks |
| **StandardScaler** | When data is **normally distributed**                                      |
| **MaxAbsScaler**   | When data is **sparse**, e.g., text data                                   |
| **RobustScaler**   | When your data has **many outliers**                                       |

---

## 🧠 Summary

- Normalization ensures fair comparison between features.
- Choosing the right scaling method can **significantly improve model performance**.
- Use `scikit-learn`’s scalers to implement easily in Python.
```