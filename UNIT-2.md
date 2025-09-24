# 📝 **Unit II – Data Structures and Functions**

---

## 🔹 Tuples

**Theory:**

* Ordered collection of elements.
* Immutable (change नहीं कर सकते).
* Define using `()`

**Example:**

```python
t = (10, 20, 30)
print(t[0])       # 10
# t[1] = 40  ❌ Error (immutable)
```

**Q:** Differentiate between list and tuple.
**A:** List is mutable, tuple is immutable.

---

## 🔹 Lists and Slicing

**Theory:**

* Ordered, mutable collection.
* Define using `[]`.
* Slicing = sub-part निकालना.

**Example:**

```python
lst = [10, 20, 30, 40, 50]
print(lst[1:4])   # [20, 30, 40]
print(lst[:3])    # [10, 20, 30]
print(lst[-2:])   # [40, 50]
```

---

## 🔹 Built-in Sequence Functions

**Common functions:**

* `len()` – length
* `max(), min()` – largest/smallest
* `sum()` – total
* `sorted()` – sort

**Example:**

```python
lst = [3, 8, 1, 6]
print(len(lst))      # 4
print(max(lst))      # 8
print(sum(lst))      # 18
print(sorted(lst))   # [1, 3, 6, 8]
```

---

## 🔹 Dictionary

**Theory:**

* Key-value pairs, unordered, mutable.
* Define using `{}`

**Example:**

```python
d = {"name": "Raj", "age": 21}
print(d["name"])         # Raj
d["age"] = 22            # update
```

**Q:** Write dictionary methods.
**A:** `keys(), values(), items(), get(), update()`

---

## 🔹 Sets

**Theory:**

* Unordered, unique elements.
* Define using `{}`
* Supports set operations (union, intersection, difference).

**Example:**

```python
s1 = {1,2,3}
s2 = {3,4,5}
print(s1 | s2)   # union {1,2,3,4,5}
print(s1 & s2)   # intersection {3}
```

---

## 🔹 List, Set, Dict Comprehensions

**Theory:** → Short way to create collections.

**Examples:**

```python
# List comprehension
squares = [x**2 for x in range(5)]
print(squares)   # [0,1,4,9,16]

# Set comprehension
evens = {x for x in range(10) if x%2==0}
print(evens)     # {0,2,4,6,8}

# Dict comprehension
d = {x: x**2 for x in range(5)}
print(d)         # {0:0,1:1,2:4,3:9,4:16}
```

---

## 🔹 Functions: Namespaces & Scope

**Theory:**

* **Namespace** = where a variable is stored.
* **Scope** = variable accessible area.
* Python follows **LEGB Rule** (Local → Enclosed → Global → Built-in).

**Example:**

```python
x = 10   # global

def outer():
    x = 20   # enclosed
    def inner():
        x = 30   # local
        print(x)
    inner()
outer()
```

👉 Output: `30`

---

## 🔹 Local Functions

**Theory:** Functions defined inside another function.

**Example:**

```python
def outer():
    def inner():
        print("I am inner")
    inner()
outer()
```

---

## 🔹 Returning Multiple Values

**Theory:** Python functions can return tuple.

**Example:**

```python
def calc(a,b):
    return a+b, a*b, a-b

s, m, d = calc(10,5)
print(s,m,d)   # 15 50 5
```

---

# ✅ Old Paper Style Questions (Unit II)

1. Differentiate between List and Tuple with example.
2. What are dictionary methods? Explain with examples.
3. Write a Python program using list comprehension to generate cubes of numbers 1–10.
4. Explain slicing in lists and tuples with example.
5. What is a namespace? Explain LEGB rule.
6. Write a function that returns sum, average, and product of three numbers.
