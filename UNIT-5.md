# 📝 **Unit V – Python Advanced Topics (Detail Notes)**

---

## 🔹 1. **Matplotlib (Graphs/Plots in Python)**

### **Definition**

Matplotlib एक Python library है जिसका काम है **ग्राफ और चार्ट बनाना**।
जैसे आप अपनी copy में graph paper पर line graph, bar graph, या pie chart बनाते हो, Python में वही काम Matplotlib करता है।

### **Why we need it?**

क्योंकि data को सिर्फ numbers में पढ़ना boring है, लेकिन अगर वही data graph बन जाए तो हमें तुरंत समझ आ जाता है।

---

### 📌 **Important Functions**

#### a) Line Plot

* जब हमें दो variables के बीच का trend दिखाना होता है।

```python
import matplotlib.pyplot as plt
x = [1,2,3,4,5]
y = [2,4,6,8,10]
plt.plot(x, y, marker='o', color='g', linestyle='--')
plt.title("Line Plot")
plt.show()
```

#### b) Bar Plot

* Categories compare करने के लिए।

```python
courses = ["BCA","BBA","BSc"]
students = [40,35,50]
plt.bar(courses, students, color='orange')
plt.show()
```

#### c) Histogram

* Continuous data को intervals (bins) में group करके frequency दिखाता है।

```python
marks = [45,50,52,60,61,62,70,72,72,75,80,82,85,88,90]
plt.hist(marks, bins=5, color='skyblue', edgecolor='black')
plt.show()
```

#### d) Scatter Plot

* दो variables के बीच relation दिखाने के लिए (dots form में)।

```python
x = [5,7,8,7,6,9]
y = [99,86,87,88,100,86]
plt.scatter(x, y, color='red')
plt.show()
```

#### e) Subplots + `tight_layout()`

* एक figure में multiple graphs डालने के लिए।

```python
import numpy as np
x = np.linspace(0,10,100)
plt.subplot(2,1,1)
plt.plot(x, np.sin(x))
plt.subplot(2,1,2)
plt.plot(x, np.cos(x))
plt.tight_layout()
plt.show()
```

---

## 🔹 2. **SciPy (Scientific Python)**

### **Definition**

SciPy = **Scientific Python**.
ये NumPy पर बनी है और इसमें **extra scientific tools** होते हैं – जैसे equations solve करना, statistics निकालना, optimization करना।

👉 सोचना: NumPy = सामान्य calculator, SciPy = scientific calculator।

---

### 📌 **Main Sub-packages of SciPy**

#### a) **Linear Algebra (`scipy.linalg`)**

* **Matrix operations** करने के लिए।
* Important tasks:

  * Determinant निकालना
  * Matrix inverse
  * Eigenvalues/Eigenvectors

```python
from scipy import linalg
import numpy as np
A = np.array([[1,2],[3,4]])
print("Determinant:", linalg.det(A))
print("Inverse:\n", linalg.inv(A))
```

---

#### b) **Statistics (`scipy.stats`)**

* Data analysis tools.
* Subtopics:

  * Mean, Median, Mode
  * Variance, Standard deviation
  * Probability distributions (Normal, Binomial, Poisson)
  * Hypothesis testing (t-test, chi-square test)

```python
from scipy import stats
data = [1,2,2,3,4,4,4,5]
print("Mode:", stats.mode(data, keepdims=True))
```

---

#### c) **Optimization (`scipy.optimize`)**

* किसी function का **minimum/maximum** निकालना।
* Root finding (equation solve करना)।

```python
from scipy.optimize import minimize
f = lambda x: (x-3)**2
res = minimize(f, 0)
print("Minimum at:", res.x)
```

---

#### d) **Integration (`scipy.integrate`)**

* Calculus के definite integrals solve करना।

```python
from scipy import integrate
result = integrate.quad(lambda x: x**2, 0, 3)
print("Integration result:", result[0])
```

---

#### e) **Fourier Transform (`scipy.fft`)**

* Signal analysis – time domain → frequency domain।

```python
from scipy.fft import fft
print(fft([1,2,3,4]))
```

---

## 🔹 3. **Scikit-learn (Machine Learning Library)**

### **Definition**

Scikit-learn = Machine Learning की library.
इसमें ready-made algorithms और tools हैं → prediction, classification, clustering।

---

### 📌 **Major Topics**

#### a) **Supervised Learning**

* Data में labels (answers) होते हैं।
* Model को train करते हैं → future data predict करता है।

**Classification:** Output categories → Spam / Not Spam
**Regression:** Output numbers → House Price

```python
from sklearn.linear_model import LinearRegression
import numpy as np
X = np.array([[1],[2],[3],[4]])
y = np.array([2,4,6,8])
model = LinearRegression().fit(X,y)
print(model.predict([[5]]))
```

---

#### b) **Unsupervised Learning**

* Data में labels नहीं होते।
* Goal = hidden patterns खोजना।

**Clustering:** Data को groups में divide करना (e.g., customer segmentation)।
**Dimensionality Reduction:** बहुत सारे features compress करना (e.g., PCA)।

---

#### c) **Preprocessing**

* Data को साफ करना:

  * Missing values handle करना
  * Scaling (सब values एक range में लाना)
  * Encoding categorical data

---

#### d) **Model Selection**

* Different models को test करना और best चुनना।
* Tools: Cross-validation, Hyperparameter tuning।

---

## 🔹 4. **NetworkX (Graph and Network Analysis)**

### **Definition**

NetworkX = Python की library **graphs और networks बनाने और analyze करने के लिए**।
Graph = Nodes (points) + Edges (connections)।

👉 Example:

* Node = व्यक्ति
* Edge = दोस्ती

---

### 📌 **Graph Types**

* **Undirected Graph** → Facebook friends (दोनों तरफ connection)।
* **Directed Graph** → Twitter follows (A→B).
* **Weighted Graph** → Road maps (distance = weight)।

---

### 📌 **Graph Terminology**

* **Node/Vertex:** एक object (city, computer, person)।
* **Edge:** दो nodes के बीच link।
* **Path:** एक node से दूसरे node तक का रास्ता।
* **Degree:** कितने connections हैं।
* **Centrality:** सबसे important node (influencer)।

---

### 📌 **Features of NetworkX**

* Graph बनाना
* Shortest path निकालना
* Centrality measure करना
* Graph visualize करना

```python
import networkx as nx
import matplotlib.pyplot as plt

G = nx.Graph()
G.add_edges_from([(1,2),(2,3),(3,4),(4,1),(1,3)])
nx.draw(G, with_labels=True, node_color="lightblue", edge_color="gray")
plt.show()

print("Shortest path 1→4:", nx.shortest_path(G, source=1, target=4))
```

---

## 🔹 5. **Errors and Exception Handling**

### Types of Errors:

* **Syntax Error** → गलत grammar (e.g., missing bracket)।
* **Runtime Error (Exception)** → code चलता है पर बीच में crash होता है।

```python
try:
    x = 10/0
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("This always runs")
```

---

## 🔹 6. **File Handling**

* **Open File:** `open("file.txt", "r")`
* **Modes:**

  * `r` → read
  * `w` → write
  * `a` → append
  * `rb`/`wb` → binary read/write

```python
with open("test.txt","w") as f:
    f.write("Hello Students!")

with open("test.txt","r") as f:
    print(f.read())
```

---

## 🔹 7. **Applications of Python**

* Web Development (Flask, Django)
* Data Science (NumPy, Pandas, Scikit-learn)
* AI/ML (TensorFlow, PyTorch)
* Automation (scripts, bots)
* Cyber Security (network tools)
* IoT (Raspberry Pi)
* Game Development (Pygame)

---

# ✅ Old Paper Style Questions (Unit V)

1. Explain line plot, bar plot, histogram, scatter plot with examples.
2. What are the main modules of SciPy? Explain with examples.
3. Differentiate between supervised and unsupervised learning in Scikit-learn.
4. Explain preprocessing and model selection in Scikit-learn.
5. What is NetworkX? Explain types of graphs with real-life examples.
6. Write a program to draw a graph using NetworkX and find shortest path.
7. Explain syntax vs runtime error in Python with examples.
8. Write a Python program to read from a file and count words.
