# Inferential Statistics & Fundamental Data Analysis in Python

Repository focused on computational statistics, probability distribution simulations, array operations with NumPy, and empirical demonstrations of fundamental mathematical concepts such as the **Central Limit Theorem (CLT)**.

---

## 📌 Table of Contents
- [Overview](#-overview)
- [Repository Structure](#-repository-structure)
- [Key Topics & Code Demonstrations](#-key-topics--code-demonstrations)
  - [1. Python Fundamentals & Array Operations](#1-python-fundamentals--array-operations)
  - [2. Central Limit Theorem (CLT) Demonstrations](#2-central-limit-theorem-clt-demonstrations)
- [Getting Started](#-getting-started)
- [Dependencies](#-dependencies)
- [License](#-license)

---

## 🔍 Overview

This repository explores core concepts in inferential statistics and scientific computing using Python. The contents bridge basic data structures and vectorization using NumPy with empirical probability experiments using Pandas, Seaborn, and Matplotlib.

---

## 📂 Repository Structure

```text
.
├── Fundamentos_Numpy_Python.ipynb   # Native Python types, lists, NumPy arrays, and reshaping operations
├── Teorema_central_del_limite.ipynb # Empirical simulation of the Central Limit Theorem
└── README.md                        # Documentation
```

---

## 💡 Key Topics & Code Demonstrations

### 1. Python Fundamentals & Array Operations
*Location: `Fundamentos_Numpy_Python.ipynb`*

Covers the fundamental differences between standard Python lists and vectorized `numpy.ndarray` operations, along with array reshaping techniques.

#### Highlights:
* **Vectorized Arithmetic vs List Concatenation:**
  ```python
  import numpy as np

  l1 = [1, 2, 3, 4, 5]
  l2 = [6, 7, 8, 9, 10]

  # Native Python Concatenation
  print(l1 + l2)  # Output: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

  # Vectorized Addition with NumPy
  arr1 = np.array(l1)
  arr2 = np.array(l2)
  print(arr1 + arr2)  # Output: [ 7  9 11 13 15]
  ```

* **Matrix Reshaping:**
  ```python
  # Generate array of numbers from 10 to 29
  data = np.array([i for i in range(10, 30)])

  # Reshape into a 5x4 matrix
  matrix_5x4 = data.reshape(5, 4)

  # Reshape into a 10x2 matrix
  matrix_10x2 = data.reshape(10, 2)
  ```

---

### 2. Central Limit Theorem (CLT) Demonstrations
*Location: `Teorema_central_del_limite.ipynb`*

Demonstrates empirically how the sampling distribution of sample means approaches a normal (Gaussian) distribution as the sample size increases, regardless of the underlying population distribution.

#### Experiments Included:
1. **Bernoulli & Binomial Sampling:**
   Generates 100 sample sets ($n=50$) from a Binomial distribution ($B(1000, 0.6)$) and plots the resulting distribution of sample means.
   
2. **Exponential Distribution Sampling:**
   Draws 100 sample sets ($n=50$) from a heavily skewed Exponential distribution ($\lambda = 1.0$) to illustrate convergence to a normal distribution of sample means under the CLT.

```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Simulate Exponential Distribution Samples
df_exp = pd.DataFrame()
for i in range(1, 101):
    df_exp[f'sample_{i}'] = np.random.exponential(scale=1.0, size=50)

# Calculate distribution of sample means
df_exp_means = pd.DataFrame({'Sample Means': df_exp.mean()})

# Visualize convergence
sns.displot(df_exp_means['Sample Means'], kde=True)
plt.title('Central Limit Theorem (Exponential Variables)')
plt.show()
```

---

## 🚀 Getting Started

To run these notebooks locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Ian-UP-0269186/Inferential_Statistics-repositorio-publico-.git
   cd Inferential_Statistics-repositorio-publico-
   ```

2. **Install required packages:**
   ```bash
   pip install numpy pandas matplotlib seaborn jupyter
   ```

3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

---

## 📦 Dependencies

- **Python** 3.8+
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Seaborn**

---

## 📄 License

This repository is available under the [MIT License](LICENSE).
