Machine Learning Implementation Notebooks

This repository contains data manipulation, exploratory data analysis (EDA), data cleaning, and fundamental machine learning algorithms implemented using Python's core data science stack.

---

## 📌 Repository Structure

```text
.
├── matches.csv              # Raw IPL dataset used for analysis
├── numpy.ipynb              # NumPy fundamentals & array operations
├── Pandas.ipynb             # Pandas EDA, data cleaning & preprocessing
└── README.md                # Project documentation
```

---

## 🛠️ Modules & Notebook Summary

### 1. NumPy Essentials (`numpy.ipynb`)
The notebook covers array creation, homogeneous type constraints, high-performance vectorized operations, array slicing, boolean masking, and matrix reshaping.

#### Key Code Snippets

* **Array Creation & Type Coercion:**
  ```python
  import numpy as np

  # Implicit string upcasting for mixed types
  narray = np.array([1, 2, 3, "hello"])
  print(narray.shape)  # Output: (4,)

  # Matrix initialization
  arr_zeros = np.zeros((3, 4))
  ```

* **Vectorized Operations:**
  ```python
  n1 = np.array([3, 4, 5])
  n2 = np.array([6, 7, 8])

  # Element-wise multiplication
  result = n1 * n2  # Output: array([18, 28, 40])
  ```

* **Slicing & Boolean Masking:**
  ```python
  arr = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9])

  # Slice elements from index 0 to 3
  print(arr[0:4])  # Output: [1 2 3 4]

  # Boolean filtering
  filtered = arr[arr > 3]  # Output: array([4, 5, 6, 7, 8, 9])
  ```

* **Reshaping Arrays:**
  ```python
  arr = np.arange(10)
  reshaped = arr.reshape(2, 5)  # Reshaped to 2x5 matrix
  ```

---

### 2. IPL Data Cleaning & EDA (`Pandas.ipynb`)
This notebook demonstrates an end-to-end data cleaning pipeline and exploratory analysis on the `matches.csv` dataset.

#### Dataset Overview
- **Initial Shape:** 1,095 rows × 20 columns
- **Cleaned Shape:** 1,028 rows × 19 columns
- **Features Included:** `id`, `season`, `city`, `date`, `match_type`, `player_of_match`, `venue`, `team1`, `team2`, `toss_winner`, `toss_decision`, `winner`, `result`, `result_margin`, `target_runs`, `target_overs`, `super_over`, `umpire1`, `umpire2`

#### Cleaning Pipeline & Code Examples

* **Data Loading & Inspection:**
  ```python
  import pandas as pd

  df = pd.read_csv("matches.csv")

  # View structural statistics
  df.head()
  df.info()
  df.describe()
  ```

* **Duplicate Check & Null Column Dropping:**
  ```python
  # Check for duplicate rows
  print(df.duplicated().sum())  # Output: 0

  # Drop sparse/unwanted feature column ('method')
  df.drop(columns="method", inplace=True)
  ```

* **Handling Missing Values:**
  ```python
  # Drop incomplete rows
  df.dropna(inplace=True)

  # Verify clean dataset
  print(df.isnull().sum())  # All 0s
  print(df.shape)         # Output: (1028, 19)
  ```

* **Indexing & Column Subsetting:**
  ```python
  # Subset specific columns
  df_subset = df[['toss_decision', 'winner', 'city']]

  # Position-based row retrieval
  first_record = df.iloc[0]
  ```

---

## 💻 Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/repository-name.git
   cd repository-name
   ```

2. **Install dependencies:**
   ```bash
   pip install numpy pandas scikit-learn matplotlib jupyter
   ```

3. **Launch Jupyter Notebooks:**
   ```bash
   jupyter notebook
   ```
