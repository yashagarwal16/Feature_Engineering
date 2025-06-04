# 🔄 Transformation in Machine Learning

## 🧠 What is Transformation?

**Transformation** refers to **changing or modifying** the values in your dataset to improve data quality or help a machine learning model **understand it better**.

It's typically applied to **features (columns)** in order to:

- Make patterns more clear  
- Reduce skewness and outliers  
- Normalize or scale data  
- Convert data into a usable format  

---

## 📌 Why Do We Use Transformations?

- ✅ Models learn better when data is **clean**, **scaled**, and **well-distributed**
- 📈 Some algorithms expect features to follow a **normal (Gaussian) distribution**
- ⚡ Helps in **speeding up training** and improving **model accuracy**

---

## 🛠️ Types of Data Transformations

### 1. 🔢 Mathematical Transformation
- Apply math functions to reduce skew or stabilize variance
- **Examples**:  
  - `log(x)`  
  - `√x`  
  - `1/x`  
  - `x²`, `x³`

---

### 2. 📏 Scaling Transformation
- Rescales numerical features to a given range
- **Examples**:
  - **Min-Max Scaling**: transforms values to [0, 1]
  - **Standardization (Z-score)**: transforms to mean = 0 and std = 1

---

### 3. 🧮 Normalization
- Makes the feature vector’s **length = 1**  
- Mostly used in algorithms like **KNN**, **SVM**, etc.

---

### 4. 🔠 Encoding Transformation
- Converts **categorical variables** into **numerical**
- **Examples**:
  - Label Encoding  
  - One-Hot Encoding  
  - Ordinal Encoding

---

### 5. 📉 Log Transformation
- Reduces **right-skewed data**
- Useful when feature values span across large ranges

---

### 6. ⚙️ Box-Cox / Yeo-Johnson
- Applies transformation to make data **more normal**
- Finds the **best-fit power transformation** automatically

---

## 🔍 Example Table

| Original | Log(x) | √x  | Scaled (0–1) |
|----------|--------|-----|--------------|
| 1        | 0.0    | 1.0 | 0.0          |
| 10       | 1.0    | 3.2 | 0.5          |
| 100      | 2.0    | 10  | 1.0          |

---

## 🖼️ Visual Placeholder

> ![Transformation Example Chart](https://via.placeholder.com/800x300?text=Transformation+Techniques+Chart)

---

## ✅ Summary

- **Transformation** = “data cleaning + reshaping”
- Makes data easier for ML models to interpret
- Different features require **different transformation strategies**
- Boosts **model performance, accuracy, and training speed**

---

## 📚 Further Reading

- [scikit-learn: Data Preprocessing](https://scikit-learn.org/stable/modules/preprocessing.html)
- [Feature Scaling and Normalization Explained](https://machinelearningmastery.com/why-data-normalization-is-important-in-machine-learning/)

