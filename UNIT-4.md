# 📝 **Unit IV – Pandas**

---

## 🔹 Introduction to Pandas

**Definition:**

* Pandas = Python की **Data Analysis Library**.
* दो main data structures:

  1. **Series** → 1D labeled array.
  2. **DataFrame** → 2D table (rows + columns).

**Import:**

```python
import pandas as pd
```

---

## 🔹 Series

**Theory:** → One-dimensional array with labels (index).

**Example:**

```python
import pandas as pd

s = pd.Series([10,20,30], index=['a','b','c'])
print(s)
```

👉 Output:

```
a    10
b    20
c    30
dtype: int64
```

---

## 🔹 DataFrame

**Theory:** → Two-dimensional, tabular data structure.

**Example:**

```python
data = {
    "Name": ["Raj","Amit","Neha"],
    "Marks": [85,90,95],
    "Course": ["BCA","BSc","BBA"]
}
df = pd.DataFrame(data)
print(df)
```

👉 Output:

```
   Name  Marks Course
0   Raj     85    BCA
1  Amit     90    BSc
2  Neha     95    BBA
```

---

## 🔹 Reading Data from CSV

```python
df = pd.read_csv("students.csv")
print(df.head())
```

---

## 🔹 DataFrame Operations

### 1. **head() and tail()**

```python
print(df.head(2))   # first 2 rows
print(df.tail(2))   # last 2 rows
```

---

### 2. **info()**

```python
print(df.info())    # summary of columns, data types, null counts
```

---

### 3. **shape**

```python
print(df.shape)     # (rows, columns)
```

---

### 4. **reshape (melt & pivot)**

* `melt()` → wide → long
* `pivot()` → long → wide

```python
pd.melt(df, id_vars=["Name"], value_vars=["Marks","Course"])
```

---

### 5. **columns**

```python
print(df.columns)   # list of column names
```

---

### 6. **isnull() & dropna()**

```python
print(df.isnull())        # True/False for null values
df2 = df.dropna()         # remove rows with NaN
```

---

### 7. **mean() & sum()**

```python
print(df["Marks"].mean())  # average
print(df["Marks"].sum())   # total
```

---

### 8. **describe()**

```python
print(df.describe())       # statistics summary
```

---

### 9. **value\_counts()**

```python
print(df["Course"].value_counts())
```

---

### 10. **corr()**

```python
print(df.corr(numeric_only=True))   # correlation matrix
```

---

### 11. **loc\[] and iloc\[]**

```python
print(df.loc[0,"Name"])      # label-based (Raj)
print(df.iloc[1,1])          # index-based (90)
```

---

### 12. **apply()**

```python
df["Grade"] = df["Marks"].apply(lambda x: "A" if x>=90 else "B")
print(df)
```

---

# ✅ Old Paper Style Questions (Unit IV)

1. Differentiate between Series and DataFrame.
2. Write a Pandas program to read a CSV file and display first 5 rows.
3. Explain `head()`, `tail()`, and `info()` functions with examples.
4. What is the use of `isnull()` and `dropna()`? Write example.
5. Write a Pandas program to calculate mean, sum, and correlation between two numeric columns.
6. Explain the difference between `loc[]` and `iloc[]`.
7. Write a Pandas program to apply a custom function on a DataFrame column.
