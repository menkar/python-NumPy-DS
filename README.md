<div align="center">

<!-- ╔══════════════════════════════════════════════╗ -->
<!-- ║           HEADER BANNER                     ║ -->
<!-- ╚══════════════════════════════════════════════╝ -->

# 🔢 Python · NumPy for Data Science

### A structured, hands-on learning repository covering NumPy fundamentals — from array creation to matrix operations and real-world exercises.

<br/>

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-22c55e?style=for-the-badge)]()

</div>

---

## 📌 Table of Contents

| # | Section |
|---|---------|
| 1 | [About the Project](#-about-the-project) |
| 2 | [Repository Structure](#-repository-structure) |
| 3 | [Learning Path](#-learning-path) |
| 4 | [Notebook Deep-Dives](#-notebook-deep-dives) |
| 5 | [Key Concepts Covered](#-key-concepts-covered) |
| 6 | [Quick Reference — NumPy Cheatsheet](#-quick-reference--numpy-cheatsheet) |
| 7 | [Getting Started](#-getting-started) |
| 8 | [Prerequisites](#-prerequisites) |
| 9 | [Author](#-author) |

---

## 🎯 About the Project

This repository is a **comprehensive, practical guide to NumPy** — the foundational numerical computing library for Python. It is designed for learners and practitioners who want to build a solid understanding of array-based computing as a stepping stone into **Data Science**, **Machine Learning**, and **Scientific Computing**.

> **NumPy** (Numerical Python) is the backbone of almost every data science library — including Pandas, Scikit-learn, TensorFlow, and PyTorch. Mastering it is non-negotiable for any data professional.

### 🌟 What makes this repository valuable?

- **Progressive structure** — Notebooks build on each other from basics to advanced operations.
- **Hands-on code** — Every concept is demonstrated with executable, commented code cells.
- **Real exercises** — Practical problems (Sudoku validation, student data analysis) reinforce theory.
- **Zero fluff** — Pure, focused NumPy learning without unnecessary abstraction.

---

## 📁 Repository Structure

```
python-NumPy-DS/
│
├── 📓 Arrays.ipynb              ← Array creation, attributes, methods & reshaping
├── 📓 array_indexing.ipynb      ← Indexing, slicing & boolean masking
├── 📓 array_operations.ipynb    ← Arithmetic, broadcasting, matrix ops & splitting
├── 📓 exercises.ipynb           ← Hands-on exercises: Sudoku + Student data
│
├── 📓 Untitled.ipynb            ← (Scratch / placeholder)
├── 📓 Untitled-1.ipynb          ← (Scratch / placeholder)
│
├── 📄 .gitignore                ← Git ignore rules
└── 📄 README.md                 ← Project documentation (this file)
```

---

## 🗺️ Learning Path

Follow the notebooks in this recommended order for the best learning experience:

```
┌─────────────────────────────────────────────────────────────────────┐
│                         LEARNING JOURNEY                            │
│                                                                     │
│  ① Arrays.ipynb          ──►  Foundation of NumPy arrays            │
│         │                                                           │
│         ▼                                                           │
│  ② array_indexing.ipynb  ──►  Access & filter array data            │
│         │                                                           │
│         ▼                                                           │
│  ③ array_operations.ipynb──►  Compute & transform arrays            │
│         │                                                           │
│         ▼                                                           │
│  ④ exercises.ipynb        ──►  Apply knowledge to real problems      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 📚 Notebook Deep-Dives

---

### 📓 1. `Arrays.ipynb` — Array Creation, Attributes & Methods

> **Purpose:** Build your first NumPy arrays and understand the core data structure.

#### 🔹 Array Creation

| Method | Description | Example |
|--------|-------------|---------|
| `np.array(list)` | Convert a Python list to an ndarray | `np.array([1, 2, 3, 4])` |
| `np.arange(start, stop)` | Range-based array | `np.arange(1, 11)` → `[1..10]` |
| `np.zeros((rows, cols))` | All-zero array | `np.zeros((4, 8))` |
| `np.ones((rows, cols))` | All-ones array | `np.ones((4, 8))` |
| `np.linspace(start, stop, n)` | `n` evenly spaced values | `np.linspace(0, 1, 100)` |

#### 🔹 Random Number Generation

| Function | Description |
|----------|-------------|
| `np.random.rand(n)` | `n` random floats in `[0, 1)` (uniform distribution) |
| `np.random.randn(n)` | `n` random floats from standard normal distribution (μ=0, σ=1) |
| `np.random.randint(low, high, n)` | `n` random integers in `[low, high)` |

```python
import numpy as np

np.random.rand(10)        # [0.88, 0.62, 0.51, ...]
np.random.randn(10)       # [-1.09, 1.06, -0.68, ...]
np.random.randint(10, 20, 10)  # [15, 18, 15, 14, ...]
```

#### 🔹 Array Attributes

| Attribute | Returns | Example |
|-----------|---------|---------|
| `.shape` | Dimensions as tuple | `(3, 3)` |
| `.size` | Total number of elements | `9` |
| `.dtype` | Data type of elements | `dtype('int64')` |

#### 🔹 Array Methods (Aggregations)

| Method | Description | Result on `[[1,2,3],[4,5,6],[7,8,9]]` |
|--------|-------------|----------------------------------------|
| `.min()` | Minimum value | `1` |
| `.max()` | Maximum value | `9` |
| `.sum()` | Sum of all elements | `45` |
| `np.sum(arr, axis=0)` | Column-wise sum | `[12, 15, 18]` |
| `np.sum(arr, axis=1)` | Row-wise sum | `[6, 15, 24]` |
| `.mean()` | Arithmetic mean | `5.0` |
| `.std()` | Standard deviation | `2.582` |
| `.argmax()` | Index of max value | `8` |
| `.argmin()` | Index of min value | `0` |

#### 🔹 Reshaping

```python
arr = np.arange(1, 31)      # Shape: (30,)
arr.reshape(6, 5)            # Shape: (6, 5) — 6 rows × 5 cols
```
> ⚠️ The total number of elements **must remain the same** when reshaping (30 = 6 × 5).

---

### 📓 2. `array_indexing.ipynb` — Indexing, Slicing & Boolean Masking

> **Purpose:** Learn to access, extract and filter specific elements from arrays.

#### 🔹 1D Vector Indexing & Slicing

```python
arr = np.arange(1, 21)   # [1, 2, 3, ..., 20]

arr[6]          # → 7            (single element)
arr[1:5]        # → [2, 3, 4, 5] (slice: start:stop)
arr[:5]         # → [1, 2, 3, 4, 5] (from beginning)
arr[3:]         # → [4, 5, ..., 20] (to end)
arr[3::2]       # → [4, 6, 8, ..., 20] (step slicing)
```

#### 🔹 2D Matrix Indexing & Slicing

```python
arr = np.arange(1, 31).reshape(6, 5)
#  [[ 1,  2,  3,  4,  5],
#   [ 6,  7,  8,  9, 10],
#   [11, 12, 13, 14, 15],
#   [16, 17, 18, 19, 20],
#   [21, 22, 23, 24, 25],
#   [26, 27, 28, 29, 30]]

arr[0]          # → [1, 2, 3, 4, 5]      (first row)
arr[5]          # → [26, 27, 28, 29, 30] (last row)
arr[0, 0]       # → 1                    (row 0, col 0)
arr[0, 4]       # → 5                    (row 0, col 4)
arr[5, 4]       # → 30                   (last element)
arr[0:2, 1:3]   # → [[2,3],[7,8]]        (sub-matrix)
arr[3:, 3:]     # → [[19,20],[24,25],[29,30]] (bottom-right block)
arr[:, 2]       # → [3, 8, 13, 18, 23, 28]   (entire column 2)
```

#### 🔹 Boolean (Conditional) Indexing

```python
arr = np.arange(11, 21)           # [11, 12, ..., 20]

bool_index = arr % 2 == 0         # [F, T, F, T, F, T, F, T, F, T]
arr[bool_index]                   # → [12, 14, 16, 18, 20]  (even numbers only)
```

> 💡 Boolean indexing is one of NumPy's most powerful features — used extensively for data filtering in Pandas and machine learning pipelines.

---

### 📓 3. `array_operations.ipynb` — Operations, Broadcasting & Matrix Math

> **Purpose:** Perform mathematical and structural transformations on arrays.

#### 🔹 Element-wise Arithmetic

```python
a1 = np.array([1, 2, 3, 4, 5])
a2 = np.array([6, 7, 8, 9, 10])

a1 + a2    # → [7,  9, 11, 13,  15]
a1 * a2    # → [6, 14, 24, 36,  50]
a1 / a2    # → [0.17, 0.29, 0.38, 0.44, 0.50]
a1 // a2   # → [0, 0, 0, 0, 0]   (floor division)
a1 ** a2   # → [1, 128, 6561, 262144, 9765625]
```

#### 🔹 Broadcasting

Broadcasting allows NumPy to perform arithmetic between arrays of **different (but compatible) shapes** without explicit loops.

```python
arr = np.array([10, 20, 30, 40])
arr + 10   # → [20, 30, 40, 50]  (scalar broadcast to all elements)

mat = np.arange(1, 26).reshape(5, 5)
mat + 10   # adds 10 to every element
mat * 2    # multiplies every element by 2
```

```
Broadcasting Rule:
  Shape (5,5)  +  Scalar (1)  →  Shape (5,5)
  Shape (5,5)  +  Shape (1,5) →  Shape (5,5)  ← row broadcast
  Shape (5,5)  +  Shape (5,1) →  Shape (5,5)  ← column broadcast
```

#### 🔹 Shallow Copy vs Deep Copy

| Operation | Shares Memory? | Modifying affects original? |
|-----------|---------------|----------------------------|
| `b = a` | ✅ Yes | ✅ Yes — both change |
| `b = a.copy()` | ❌ No | ❌ No — independent |

```python
# Shallow — b and a point to the same data
a = np.arange(1, 26)
b = a
b[0] = 99         # a[0] is also 99!

# Deep — independent copy
arr1 = np.arange(1, 26)
b = arr1.copy()
b[0] = 101        # arr1[0] is still 1 ✔
```

#### 🔹 Matrix Operations

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

A * B          # Element-wise: [[5,12],[21,32]]
A @ B          # Matrix multiply: [[19,22],[43,50]]
np.dot(A, B)   # Same as A @ B
A.T            # Transpose: [[1,3],[2,4]]
```

#### 🔹 Stacking Arrays

| Function | Direction | Output Shape |
|----------|-----------|--------------|
| `np.vstack((a, b))` | Vertical (row-wise) | `(2, n)` |
| `np.hstack((a, b))` | Horizontal (column-wise) | `(2n,)` |
| `np.column_stack((a, b))` | Side by side as columns | `(n, 2)` |

```python
a = np.array([1, 2, 3, 4])
b = np.array([5, 6, 7, 8])

np.vstack((a, b))        # [[1,2,3,4], [5,6,7,8]]
np.hstack((a, b))        # [1,2,3,4,5,6,7,8]
np.column_stack((a, b))  # [[1,5],[2,6],[3,7],[4,8]]
```

#### 🔹 Splitting Arrays

> ⚠️ Splits **must be equal** — NumPy raises an error for unequal divisions.

```python
c = np.arange(16).reshape(4, 4)

np.hsplit(c, 2)   # 2 arrays of shape (4,2) — horizontal split
np.hsplit(c, 4)   # 4 arrays of shape (4,1)
np.vsplit(c, 2)   # 2 arrays of shape (2,4) — vertical split
np.vsplit(c, 4)   # 4 arrays of shape (1,4)
```

---

### 📓 4. `exercises.ipynb` — Hands-on Practice Problems

> **Purpose:** Apply NumPy knowledge to solve real-world-style problems.

---

#### 🧩 Exercise A — Sudoku Validator

**Problem:** Given a completed 9×9 Sudoku board, validate it by checking that every row, every column, and every 3×3 sub-grid sums to **45** (i.e., contains digits 1–9 exactly once).

```python
# Approach
s = np.array([...])   # 9×9 valid Sudoku grid

# 1. Row validation
row_sums = np.sum(s, axis=1)      # Each row must sum to 45
print(np.all(row_sums == 45))      # True → valid rows

# 2. Column validation
col_sums = np.sum(s, axis=0)
print(np.all(col_sums == 45))      # True → valid columns

# 3. Sub-grid (3×3 box) validation
for i in range(0, 9, 3):
    for j in range(0, 9, 3):
        box = s[i:i+3, j:j+3]
        print(box.sum())            # Must print 45 for all 9 boxes
```

**Skills demonstrated:** 2D slicing, `axis` parameter, `np.all()`, nested loops over grid sections.

---

#### 📊 Exercise B — Student Marks Analysis

**Dataset:**

| Student | Age | Math Marks | Science Marks |
|---------|-----|-----------|---------------|
| 1 | 18 | 85 | 78 |
| 2 | 19 | 92 | 88 |
| 3 | 17 | 76 | 95 |
| 4 | 18 | 65 | 70 |
| 5 | 20 | 90 | 85 |

**Queries solved:**

| # | Query | NumPy Code | Result |
|---|-------|------------|--------|
| 1 | Shape of the matrix | `data.shape` | `(5, 3)` |
| 2 | Average age | `np.mean(data[:, 0])` | `18.4` |
| 3 | All math marks | `data[:, 1]` | `[85, 92, 76, 65, 90]` |
| 4 | Highest science mark | `np.max(data[:, 2])` | `95` |
| 5 | Students with Math > 90 | `data[data[:, 1] > 90]` | `[[19, 92, 88]]` |
| 6 | Increase all Math marks by 5 | `data[:, 1] += 5` | `[90, 97, 81, 70, 95]` |
| 7 | Students younger than 19 | `len(data[data[:, 0] < 19])` | `3` |
| 8 | Average marks per subject | `np.mean(data[:, 1:], axis=0)` | `[86.6, 83.2]` |
| 9 | Students scoring ≥ 80 in both | `data[(data[:,1]>=80) & (data[:,2]>=80)]` | 3 students |
| 10 | Set Science marks < 75 to 0 | `data[:,2][data[:,2] < 75] = 0` | Student 4 → `0` |

**Skills demonstrated:** Column extraction, boolean indexing, compound conditions (`&`), in-place modification, `np.mean` with `axis`.

---

## 🧠 Key Concepts Covered

```
┌─────────────────────────────────────────────────────────────────────────┐
│                     NUMPY CONCEPTS OVERVIEW                             │
├────────────────────────┬────────────────────────────────────────────────┤
│  ARRAY CREATION        │  np.array, arange, zeros, ones, linspace,      │
│                        │  rand, randn, randint                          │
├────────────────────────┼────────────────────────────────────────────────┤
│  ARRAY ATTRIBUTES      │  .shape, .size, .dtype, .ndim                  │
├────────────────────────┼────────────────────────────────────────────────┤
│  AGGREGATION           │  min, max, sum, mean, std, argmin, argmax      │
│                        │  (global and axis-specific)                    │
├────────────────────────┼────────────────────────────────────────────────┤
│  RESHAPING             │  .reshape(rows, cols)                           │
├────────────────────────┼────────────────────────────────────────────────┤
│  INDEXING & SLICING    │  arr[i], arr[i:j], arr[::step],               │
│                        │  matrix[row, col], matrix[r1:r2, c1:c2]       │
├────────────────────────┼────────────────────────────────────────────────┤
│  BOOLEAN INDEXING      │  arr[arr > threshold], compound conditions      │
├────────────────────────┼────────────────────────────────────────────────┤
│  ARITHMETIC            │  +, -, *, /, //, ** (element-wise)             │
├────────────────────────┼────────────────────────────────────────────────┤
│  BROADCASTING          │  Scalar, row-vector, column-vector broadcast    │
├────────────────────────┼────────────────────────────────────────────────┤
│  COPY SEMANTICS        │  Shallow copy (=), Deep copy (.copy())         │
├────────────────────────┼────────────────────────────────────────────────┤
│  MATRIX OPS            │  *, @, np.dot, .T (transpose)                  │
├────────────────────────┼────────────────────────────────────────────────┤
│  STACKING              │  vstack, hstack, column_stack                   │
├────────────────────────┼────────────────────────────────────────────────┤
│  SPLITTING             │  hsplit, vsplit (equal divisions only)         │
└────────────────────────┴────────────────────────────────────────────────┘
```

---

## 📋 Quick Reference — NumPy Cheatsheet

```python
import numpy as np

# ── Creation ─────────────────────────────────────────────────────────
np.array([1, 2, 3])                 # From list
np.arange(start, stop, step)        # Like Python range
np.zeros((3, 4))                    # 3×4 zeros
np.ones((3, 4))                     # 3×4 ones
np.linspace(0, 1, 50)               # 50 evenly spaced pts
np.random.rand(5)                   # 5 uniform random [0,1)
np.random.randn(5)                  # 5 standard normal
np.random.randint(0, 10, 5)         # 5 random integers

# ── Attributes ───────────────────────────────────────────────────────
arr.shape     # (rows, cols)
arr.size      # total elements
arr.dtype     # data type
arr.ndim      # number of dimensions

# ── Reshape ──────────────────────────────────────────────────────────
arr.reshape(r, c)                   # Must: r * c == arr.size

# ── Indexing & Slicing ───────────────────────────────────────────────
arr[i]                              # 1D: element at index i
arr[i:j]                            # 1D: slice from i to j-1
arr[i::step]                        # 1D: step slice
arr[r, c]                           # 2D: element at (r,c)
arr[r1:r2, c1:c2]                   # 2D: sub-matrix
arr[:, c]                           # 2D: entire column c
arr[arr > val]                      # Boolean mask
arr[(arr > a) & (arr < b)]          # Compound condition

# ── Aggregation ──────────────────────────────────────────────────────
arr.min(), arr.max()
arr.sum(), arr.mean(), arr.std()
arr.argmin(), arr.argmax()
np.sum(arr, axis=0)                 # Column-wise
np.sum(arr, axis=1)                 # Row-wise

# ── Arithmetic ───────────────────────────────────────────────────────
a + b, a - b, a * b, a / b, a ** b  # Element-wise
arr + scalar                        # Broadcasting

# ── Matrix Ops ───────────────────────────────────────────────────────
A @ B           # Matrix multiplication
np.dot(A, B)    # Same as A @ B
A.T             # Transpose

# ── Copy ─────────────────────────────────────────────────────────────
b = a           # Shallow (shared memory)
b = a.copy()    # Deep (independent)

# ── Stack & Split ────────────────────────────────────────────────────
np.vstack((a, b))         # Stack rows
np.hstack((a, b))         # Stack columns
np.column_stack((a, b))   # Side by side
np.hsplit(arr, n)          # n horizontal splits
np.vsplit(arr, n)          # n vertical splits
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/python-NumPy-DS.git
cd python-NumPy-DS
```

### 2. Create a Virtual Environment (Recommended)

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install numpy jupyter
```

Or create a `requirements.txt` and install:

```
numpy>=1.24.0
jupyter>=1.0.0
```

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Then open any `.ipynb` file from the browser interface.

---

## 📦 Prerequisites

| Tool | Minimum Version | Purpose |
|------|----------------|---------|
| Python | 3.8+ | Runtime |
| NumPy | 1.24+ | Numerical computing |
| Jupyter | 1.0+ | Interactive notebooks |
| pip | Latest | Package installation |

> 💡 All notebooks import NumPy as `import numpy as np` — the standard convention.

---

## 📂 File Reference

| File | Lines of Code | Topics |
|------|--------------|--------|
| `Arrays.ipynb` | ~40 cells | Creation, attributes, aggregation, reshape |
| `array_indexing.ipynb` | ~26 cells | 1D/2D indexing, slicing, boolean masks |
| `array_operations.ipynb` | ~60 cells | Arithmetic, broadcasting, copy, matrix ops, stack/split |
| `exercises.ipynb` | ~41 cells | Sudoku validator, student marks analysis |

---

## 👤 Author

<div align="center">

---

### Swapnil Menkar

*Data Science Enthusiast · Python Developer*

---

</div>

| | |
|---|---|
| 📱 **Mobile** | [+91 81490 05578](tel:+918149005578) |
| 💼 **LinkedIn** | [linkedin.com/in/swapnil-menkar-7051852b](https://www.linkedin.com/in/swapnil-menkar-7051852b/) |
| 🐙 **GitHub** | [github.com/swapnil-menkar](https://github.com/swapnil-menkar) |

---

<div align="center">

> *"NumPy is to Python what a foundation is to a building — everything stands on it."*

<br/>

**⭐ If you found this helpful, consider giving the repository a star!**

</div>
