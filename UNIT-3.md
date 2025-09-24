# 📝 **Unit III – Functions, Objects and NumPy**

---

## 🔹 Anonymous (Lambda) Functions

**Definition:**

* **Lambda function** एक छोटा, **one-line anonymous function** होता है।
* इसे `lambda` keyword से define करते हैं।
* Syntax:

```python
lambda arguments: expression
```

**Theory:**

* Useful जब function temporary चाहिए।
* Return automatically होता है (return keyword लिखने की जरूरत नहीं)।

**Example:**

```python
square = lambda x: x**2
print(square(5))   # 25
```

**Q (Old paper):** What is a lambda function? Write example.
**A:** Lambda is an anonymous function used for small tasks. Example above.

---

## 🔹 Partial Argument Application

**Definition:**

* जब किसी function के कुछ arguments **fix** कर देते हैं और नया function बना लेते हैं।
* Python में `functools.partial()` से होता है।

**Theory:**

* Useful for reusing a function with default/fixed values।

**Example:**

```python
from functools import partial

def power(base, exp):
    return base**exp

square = partial(power, exp=2)   # exp fix कर दिया
print(square(5))   # 25
```

---

## 🔹 Generators

**Definition:**

* Special functions जो values को **yield** करते हैं (one at a time)।
* Memory efficient होते हैं।

**Theory:**

* Normal function `return` करता है।
* Generator function `yield` keyword use करता है।

**Example:**

```python
def counter():
    for i in range(5):
        yield i

for n in counter():
    print(n)
```

👉 Output: 0 1 2 3 4

---

## 🔹 Objects and Methods in Python

**Definition:**

* **Object** → किसी class का instance।
* **Method** → function जो object पर काम करता है।

**Theory:**

* Python में हर चीज object है (int, str, list भी)।
* Methods = object से जुड़े functions।

**Example:**

```python
name = "python"
print(name.upper())   # method call → "PYTHON"
```

---

# 🧮 **NumPy (Numerical Python)**

---

## 🔹 Creating N-dimensional Arrays

**Definition:**

* `numpy.array()` से arrays create होते हैं।
* 1D, 2D, multi-dimensional arrays बना सकते हैं।

**Examples:**

```python
import numpy as np

arr1 = np.array([1,2,3])             # 1D array
arr2 = np.array([[1,2],[3,4]])       # 2D array
arr3 = np.zeros((2,3))               # 2x3 matrix of 0s
arr4 = np.ones((2,2))                # 2x2 matrix of 1s
arr5 = np.eye(3)                     # Identity matrix
```

---

## 🔹 Arithmetic with NumPy Arrays

**Theory:**

* Operations element-wise होते हैं।
* बहुत fast होते हैं normal Python loops से।

**Example:**

```python
a = np.array([1,2,3])
b = np.array([4,5,6])

print(a + b)   # [5 7 9]
print(a * b)   # [ 4 10 18]
print(a ** 2)  # [1 4 9]
```

---

## 🔹 Basic Indexing and Slicing

**Theory:**

* Arrays me indexing 0 से start होती है।
* 2D arrays → `[row, column]` notation।

**Example:**

```python
arr = np.array([[10,20,30],[40,50,60],[70,80,90]])

print(arr[0,1])     # 20
print(arr[1,:])     # [40 50 60] → full row
print(arr[:,2])     # [30 60 90] → full column
```

---

## 🔹 Pseudorandom Number Generation

**Definition:**

* NumPy ke `random` module se random numbers generate kar सकते हैं।

**Examples:**

```python
print(np.random.rand(3))         # [0.12 0.55 0.77] random floats
print(np.random.randint(1,10,5)) # [3 8 1 9 6] random integers
print(np.random.randn(2,2))      # normal distribution 2x2 matrix
```

---

# ✅ Old Paper Style Questions (Unit III)

1. What is a lambda function? Write its syntax and example.
2. Explain partial argument application with example.
3. Write a generator function to print first 10 even numbers.
4. Differentiate between return and yield.
5. Write a NumPy program to create a 3×3 identity matrix.
6. Explain array slicing in NumPy with example.
7. Write a NumPy program to generate 5 random integers between 1 and 50.
