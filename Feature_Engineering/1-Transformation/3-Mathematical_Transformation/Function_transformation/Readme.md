# 🔧 Function Transformation in Machine Learning

## 🧠 What is Function Transformation?

**Function Transformation** means applying **math functions** to your data to fix skew, reduce outliers, or make patterns clearer for models.

---

## 🛠️ Types of Function Transformations (with visuals)

### 1. 🔹 Logarithmic Transformation

```

f(x) = log(x)

```

- Compresses large values  
- Works only for **x > 0**

**Visual Example:**

Original values: 1, 10, 100, 1000  
Transformed (log base 10):

```

1     -> 0
10    -> 1
100   -> 2
1000  -> 3

```

**Plot:**

```

Original:    | \*         \*          \*           \*
Transformed: | \*     \*     \*     \*

```

---

### 2. 🔹 Square Root Transformation

```

f(x) = √x

```

- Gently reduces skew

**Visual Example:**

Original: 1, 4, 9, 16  
Transformed:

```

1  -> 1
4  -> 2
9  -> 3
16 -> 4

```

**Plot:**

```

Original:    | \*   \*     \*       \*
Transformed: | \*   \*     \*       \*

```

(Similar shape but smoother scale)

---

### 3. 🔹 Reciprocal Transformation

```

f(x) = 1 / x

```

- Flips and shrinks large values

**Visual Example:**

Original: 1, 2, 5, 10  
Transformed:

```

1  -> 1
2  -> 0.5
5  -> 0.2
10 -> 0.1

```

**Plot:**

```

Original:    | \*    \*       \*            \*
Transformed: | \*    \*       \*            \*

```

(Value decreases as x increases)

---

### 4. 🔹 Power Transformation (Square)

```

f(x) = x²

```

- Expands differences between values

**Visual Example:**

Original: 1, 2, 3, 4  
Transformed:

```

1 -> 1
2 -> 4
3 -> 9
4 -> 16

```

**Plot:**

```

Original:    | \*    \*       \*           \*
Transformed: | \*         \*           \*             \*

```

---

## ✅ Summary Table

| Transformation    | Function           | Transformed Value Example (x=4) |
|-------------------|--------------------|---------------------------------|
| Logarithmic       | log(x)             | 0.6 (log base e)                |
| Square Root       | √x                 | 2                               |
| Reciprocal        | 1/x                | 0.25                            |
| Power (Square)    | x²                 | 16                              |

---

## 🧠 When to Use?

- Data skewed or has outliers  
- Want to reduce impact of large values  
- Improve model performance

---

**Transformations change the shape of data, helping models learn better!**
```
