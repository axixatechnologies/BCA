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


### 📌 List Methods

#### 1. `append(x)`

* **Adds** item at the **end**.
* Param → `x` (any type).
* Return → `None`.
* Error → कभी नहीं।

```python
lst = [1,2,3]
lst.append(4)
print(lst)   # [1,2,3,4]
```

---

#### 2. `extend(iterable)`

* **Adds multiple items** at end.
* Param → iterable (list, tuple, set, string).
* Return → `None`.
* Error → अगर non-iterable दोगे।

```python
lst = [1,2]
lst.extend([3,4])
print(lst)   # [1,2,3,4]
lst.extend("hi")
print(lst)   # [1,2,3,4,'h','i']
```

---

#### 3. `insert(i, x)`

* किसी specific index `i` पर element डालना।
* Param → index, value.
* Return → `None`.
* Error → Index out of range नहीं होता (end पर add कर देगा)।

```python
lst = [1,2,3]
lst.insert(1,99)
print(lst)   # [1,99,2,3]
```

---

#### 4. `remove(x)`

* पहली बार आने वाला value हटाता है।
* Param → value.
* Error → अगर value list में नहीं है तो `ValueError`।

```python
lst = [1,2,3,2]
lst.remove(2)
print(lst)   # [1,3,2]
# lst.remove(10) → ValueError
```

---

#### 5. `pop(i=-1)`

* Element निकालकर return करता है।
* Param → index (default last).
* Error → अगर index invalid हो।

```python
lst = [1,2,3]
print(lst.pop())    # 3
print(lst.pop(0))   # 1
# lst.pop(10) → IndexError
```

---

#### 6. `clear()`

* List खाली कर देता है।
* Return → `None`.

```python
lst = [1,2,3]
lst.clear()
print(lst)   # []
```

---

#### 7. `index(x, start=0, end=len(lst))`

* Value की पहली position देता है।
* Param → value, optional start & end.
* Error → Value नहीं मिला तो `ValueError`।

```python
lst = [10,20,30,20]
print(lst.index(20))       # 1
print(lst.index(20,2))     # 3
# lst.index(50) → ValueError
```

---

#### 8. `count(x)`

* कितनी बार value आई है।

```python
lst = [1,2,2,3]
print(lst.count(2))   # 2
```

---

#### 9. `sort(reverse=False, key=None)`

* List को sort करता है।
* Param:

  * `reverse=True` → descending
  * `key=function` → custom sorting
* Error → अगर list में mixed types हों।

```python
lst = [3,1,4,2]
lst.sort()
print(lst)    # [1,2,3,4]
lst.sort(reverse=True)
print(lst)    # [4,3,2,1]
```

---

#### 10. `reverse()`

* Order उल्टा कर देता है।

```python
lst = [1,2,3]
lst.reverse()
print(lst)   # [3,2,1]
```

---

#### 11. `copy()`

* Shallow copy देता है।

```python
lst1 = [1,2]
lst2 = lst1.copy()
print(lst2)   # [1,2]
```

---

## 🔹 2. **Tuple**

**Definition:** Ordered, immutable collection.
Syntax: `t = (1,2,3)`

### 📌 Tuple Methods

(बहुत कम होते हैं क्योंकि immutable है)

1. `count(x)` → कितनी बार आता है।
2. `index(x)` → पहली position।

```python
t = (1,2,2,3)
print(t.count(2))   # 2
print(t.index(3))   # 3
```

---

## 🔹 3. **Dictionary**

**Definition:** Key-Value pairs.
Syntax: `d = {"a":1, "b":2}`

---

### 📌 Dictionary Methods

#### 1. `get(key, default=None)`

* Key का value देता है।
* अगर key नहीं है तो `default` return करता है (Error नहीं देगा)।

```python
d = {"a":1}
print(d.get("a"))        # 1
print(d.get("z","NA"))   # NA
```

---

#### 2. `keys()`, `values()`, `items()`

* All keys, values, key-value pairs।

```python
d = {"a":1,"b":2}
print(d.keys())    # dict_keys(['a','b'])
print(d.values())  # dict_values([1,2])
print(d.items())   # dict_items([('a',1),('b',2)])
```

---

#### 3. `update(other)`

* Dictionary merge करता है।

```python
d = {"a":1}
d.update({"b":2})
print(d)   # {'a':1,'b':2}
```

---

#### 4. `pop(key, default)`

* Key हटाकर value return करता है।
* Error → अगर key नहीं है और default नहीं दिया।

```python
d = {"a":1,"b":2}
print(d.pop("a"))     # 1
# print(d.pop("z"))   → KeyError
print(d.pop("z",0))   # 0
```

---

#### 5. `popitem()`

* Last inserted item remove करता है।
* Empty dict पर error देगा।

```python
d = {"a":1,"b":2}
print(d.popitem())   # ('b',2)
```

---

#### 6. `clear()`

* Dict खाली।

```python
d = {"a":1}
d.clear()
print(d)   # {}
```

---

## 🔹 4. **Set**

**Definition:** Unordered, unique elements.
Syntax: `s = {1,2,3}`

---

### 📌 Set Methods

#### 1. `add(x)`

* एक element add करता है।

```python
s = {1,2}
s.add(3)
print(s)   # {1,2,3}
```

---

#### 2. `update(iterable)`

* Multiple elements add।

```python
s = {1}
s.update([2,3])
print(s)   # {1,2,3}
```

---

#### 3. `remove(x)`

* Element हटाता है।
* Error → अगर element नहीं है।

```python
s = {1,2}
s.remove(2)
# s.remove(5) → KeyError
```

---

#### 4. `discard(x)`

* Element हटाता है।
* Error → कभी नहीं देगा।

```python
s = {1,2}
s.discard(5)   # No error
```

---

#### 5. `pop()`

* कोई random element हटाता है।
* Empty set पर error।

```python
s = {1,2}
print(s.pop())    # 1 या 2
```

---

#### 6. `clear()`

* Set empty।

---

#### 7. Set Operations

* `union()` → |
* `intersection()` → &
* `difference()` → -
* `symmetric_difference()` → ^

```python
s1 = {1,2,3}
s2 = {3,4}
print(s1 | s2)   # {1,2,3,4}
print(s1 & s2)   # {3}
```




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
