# 📝 **Unit I – Basics**

---

## 🔹 Python Interpreter

**Theory:**

* Interpreter → line-by-line code execute करता है.
* Compiler → पूरा code compile करके फिर चलाता है.
* Python uses **interpreter** (CPython by default).

**Example:**

```python
print("Hello World")
```

👉 Python interpreter इस code को line-by-line चलाएगा।

Q: Differentiate between interpreter and compiler in Python.
**Answer:**

* Interpreter executes code line by line (Python).
* Compiler translates whole code at once (C/C++).

---

## 🔹 Writing Code in Jupyter Notebook

**Theory:**

* Jupyter Notebook → interactive environment for Python.
* Cells में code + output + notes लिख सकते हैं.

**Example:**

```python
a = 10
b = 20
print("Sum =", a+b)
```

**Q:** How is Jupyter Notebook different from VS Code?
**A:**

* Jupyter → interactive, used in data science.
* VS Code → general IDE, code + projects.

---

## 🔹 Indentation

**Theory:**

* Python में blocks को `{ }` से नहीं बल्कि **indentation (spaces/tabs)** से define किया जाता है।

**Example:**

```python
if True:
    print("This is inside block")
print("This is outside block")
```

**Q:** What will happen if indentation is missing?
**A:** SyntaxError आएगा।

---

## 🔹 Comments

**Theory:**

* Single line → `#`
* Multi-line → triple quotes `'''  '''`

**Example:**

```python
# This is single line comment
'''
This is
multi-line comment
'''
```

---

## 🔹 Importing a Module

**Theory:**

* Module = pre-written Python file (.py) with functions.
* Import करके उसका use कर सकते हैं।

**Example:**

```python
import math
print(math.sqrt(16))
```

---

## 🔹 Binary Operators

**Theory:**

* Arithmetic: `+ - * / // % **`
* Comparison: `== != > < >= <=`
* Logical: `and or not`
* Bitwise: `& | ^ ~ << >>`

**Example:**

```python
a, b = 10, 3
print(a+b, a//b, a**b)
```

---

## 🔹 Standard Scalar Data Types

* `int`, `float`, `complex`, `bool`, `str`
* (List/tuple set dict → scalar नहीं, ये collections हैं)

**Example:**

```python
x = 10        # int
y = 3.14      # float
z = 2 + 3j    # complex
flag = True   # bool
s = "Hello"   # str
```

---

## 🔹 Type Casting

**Theory:** → ek type se dusre me convert karna.
**Example:**

```python
a = "100"
print(int(a) + 20)   # 120
```

---

## 🔹 if-else Statements

**Example:**

```python
x = 5
if x % 2 == 0:
    print("Even")
else:
    print("Odd")
```

---

## 🔹 Loops (while, for)

```python
for i in range(1,6):
    print(i)

i = 1
while i <= 5:
    print(i)
    i += 1
```

---

## 🔹 pass Statement

* Placeholder when no code inside block.

```python
for i in range(5):
    pass
```

---

## 🔹 range()

```python
print(list(range(1,10,2)))   # [1,3,5,7,9]
```

---

## 🔹 Ternary Expressions

```python
x = 10
result = "Even" if x%2==0 else "Odd"
print(result)
```

---

# ✅ Old Paper Style Questions (Unit I)

1. Explain the role of indentation in Python.
2. Differentiate between interpreter and compiler.
3. Write a program to check whether a number is prime.
4. Explain `range()` with suitable examples.
5. What is the purpose of `pass` statement?
6. Differentiate between binary and logical operators.
