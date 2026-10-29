# Task 20: Sort Dataset

## Overview
This task focuses on sorting tabular datasets using the Pandas library in Python. Sorting is a fundamental data manipulation technique used to organize numerical and categorical data for clearer analysis and reporting.

---

## Objectives
* Understand how sorting helps structure and analyze datasets.
* Master single-column ascending and descending sorting.
* Learn multi-column sorting with mixed sort orders (ascending vs. descending).

---

## Tools & Technologies Used
* **Language:** Python
* **Library:** Pandas
* **Environment:** Jupyter Notebook

---

## Dataset Structure
The task utilizes an **Employee Dataset** generated dynamically within the notebook:

| Column Name  | Data Type   | Description                       |
| :----------- | :---------- | :-------------------------------- |
| `Employee_ID`| Integer     | Unique identifier for employees  |
| `Name`       | String      | Employee full name                |
| `Department` | String      | Department name (e.g., IT, HR)    |
| `Age`        | Integer     | Age of the employee               |
| `Salary`     | Integer     | Annual salary of the employee     |

---

## Implementation & Code

```python
import pandas as pd

# 1. Create Sample Employee Dataset
data = {
    'Employee_ID': [101, 102, 103, 104, 105, 106, 107, 108],
    'Name': ['Alice', 'Bob', 'Charlie', 'Diana', 'Ethan', 'Fiona', 'George', 'Hannah'],
    'Department': ['IT', 'HR', 'IT', 'Finance', 'HR', 'Finance', 'IT', 'HR'],
    'Age': [28, 34, 25, 42, 30, 26, 38, 29],
    'Salary': [65000, 55000, 70000, 90000, 58000, 62000, 85000, 56000]
}

df = pd.DataFrame(data)

# 2. Ascending Sort by Age
sorted_asc = df.sort_values(by='Age')

# 3. Descending Sort by Salary
sorted_desc = df.sort_values(by='Salary', ascending=False)

# 4. Multi-column Sort (Department Ascending, Salary Descending)
sorted_multi = df.sort_values(by=['Department', 'Salary'], ascending=[True, False])
```

---

## Results & Deliverables

### 1. Ascending Sort (by Age - Lowest to Highest)
```text
   Employee_ID     Name Department  Age  Salary
2          103  Charlie         IT   25   70000
5          106    Fiona    Finance   26   62000
0          101    Alice         IT   28   65000
7          108   Hannah         HR   29   56000
4          105    Ethan         HR   30   58000
1          102      Bob         HR   34   55000
6          107   George         IT   38   85000
3          104    Diana    Finance   42   90000
```

### 2. Descending Sort (by Salary - Highest to Lowest)
```text
   Employee_ID     Name Department  Age  Salary
3          104    Diana    Finance   42   90000
6          107   George         IT   38   85000
2          103  Charlie         IT   25   70000
0          101    Alice         IT   28   65000
5          106    Fiona    Finance   26   62000
4          105    Ethan         HR   30   58000
7          108   Hannah         HR   29   56000
1          102      Bob         HR   34   55000
```

### 3. Multi-Column Sort (Department Ascending, Salary Descending)
```text
   Employee_ID     Name Department  Age  Salary
3          104    Diana    Finance   42   90000
5          106    Fiona    Finance   26   62000
4          105    Ethan         HR   30   58000
7          108   Hannah         HR   29   56000
1          102      Bob         HR   34   55000
6          107   George         IT   38   85000
2          103  Charlie         IT   25   70000
0          101    Alice         IT   28   65000
```

---

## Interview Questions & Answers

### Q1: How do you sort a DataFrame?
**Answer:**  
You sort a Pandas DataFrame using the `.sort_values()` method by specifying the column name or list of column names in the `by` parameter.  
*Example:* `df.sort_values(by='Age')`

### Q2: What does `ascending=False` do?
**Answer:**  
Setting `ascending=False` inside `.sort_values()` sorts the data in **descending order** (from largest to smallest for numerical values, or Z to A for categorical/string values). By default, `ascending` is set to `True`.

### Q3: Can a DataFrame be sorted by multiple columns?
**Answer:**  
Yes, a DataFrame can be sorted by multiple columns by passing a list of column names to the `by` parameter. You can also specify different sort orders for each column by passing a corresponding list of booleans to the `ascending` parameter.  
*Example:* `df.sort_values(by=['Department', 'Salary'], ascending=[True, False])`
