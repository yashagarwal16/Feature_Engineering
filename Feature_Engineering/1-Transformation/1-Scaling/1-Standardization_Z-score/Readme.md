### 📊 What is **Standardization**?

**Standardization** (also called **Z-score normalization**) is a **feature scaling technique** that transforms data to have:

- **Mean (average) = 0**
- **Standard Deviation = 1**

---

### 📐 Formula:

$$
z = \frac{x - \mu}{\sigma}
$$

Where:

- $x$ = original value  
- $\mu$ = mean of the feature  
- $\sigma$ = standard deviation of the feature

---

### 🔍 Simple Example:

Feature **Height (cm)** with mean = 160 and std dev = 10:

| Height (cm) | Standardized Value (z)           |
|-------------|---------------------------------|
| 150         | \( (150 - 160) / 10 = -1 \)     |
| 160         | \( (160 - 160) / 10 = 0 \)      |
| 170         | \( (170 - 160) / 10 = 1 \)      |

Resulting transformed feature: **[-1, 0, 1]**

---

### ✅ Why Use Standardization?

- Centers data around **0** with **unit variance**.
- Useful for algorithms assuming **normal distribution**.
- Important for models sensitive to feature scale, such as:

  - Logistic Regression  
  - Support Vector Machines (SVM)  
  - K-Nearest Neighbors (KNN)  
  - Neural Networks  
  - Principal Component Analysis (PCA)

---

### 💡 Example in Python (`sklearn`):

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaled_data = scaler.fit_transform(data)
````

```

---
