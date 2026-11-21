# 🚗 Driver Data Analysis Using Python

## 📌 Project Overview

This project focuses on analyzing driver data using Python, Pandas, and NumPy. It explores the relationship between average daily driving distance and the percentage of time spent over the speed limit.

The project includes data exploration, data cleaning, statistical analysis, sorting, filtering, speed categorization, distance categorization, grouping, aggregation, and correlation analysis to identify meaningful patterns in driver data.

## 🎯 Project Objectives

- Analyze average daily driving distance.
- Analyze the percentage of time spent over the speed limit.
- Identify the top 10 drivers based on daily driving distance.
- Identify the top 10 drivers based on speeding percentage.
- Filter drivers based on specific driving conditions.
- Categorize drivers based on speeding percentage.
- Classify drivers based on daily driving distance.
- Explore the correlation between driving distance and speeding percentage.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Jupyter Notebook

## 📂 Dataset Information

The dataset contains the following columns:

| Column Name | Description |
|---|---|
| `mean_dist_day` | Average daily driving distance |
| `mean_over_speed_perc` | Percentage of time spent over the speed limit |

## ⚙️ Project Workflow

### 1. Import Libraries

Imported Pandas and NumPy for data manipulation and analysis.

```python
import pandas as pd
import numpy as np
```

### 2. Load Dataset

Loaded the driver dataset using Pandas.

```python
df = pd.read_csv("driver.csv")
```

### 3. Data Exploration

Explored the dataset using the following methods:

- `head()` – Displays the first five rows.
- `tail()` – Displays the last five rows.
- `columns` – Displays column names.
- `shape` – Displays the number of rows and columns.
- `dtypes` – Checks data types.
- `isnull().sum()` – Checks missing values.

### 4. Data Cleaning

Created a copy of the original dataset and removed duplicate records.

```python
data = df.copy()
data = data.drop_duplicates()
```

### 5. Statistical Analysis

Performed descriptive statistical analysis using:

```python
data.describe()
```

Calculated:
- Mean daily driving distance.
- Mean speeding percentage.
- Maximum daily driving distance.
- Minimum daily driving distance.
- Maximum speeding percentage.
- Minimum speeding percentage.

### 6. Sorting and Filtering

Performed sorting and filtering operations:

- Selected the top 10 drivers based on daily driving distance.
- Selected the top 10 drivers based on speeding percentage.
- Filtered drivers with speeding percentages greater than 50%.
- Filtered drivers with daily driving distances greater than 100.
- Identified drivers satisfying both conditions.

### 7. Speed Categorization

Used `pd.cut()` to categorize drivers based on their speeding percentage.

```python
data["speed_category"] = pd.cut(
    data["mean_over_speed_perc"],
    bins=[-1, 5, 10, 20, 50, 100],
    labels=["0-5", "6-10", "11-20", "21-50", "51-100"]
)
```

Used `value_counts()` to count the number of drivers in each speed category.

### 8. Grouping and Aggregation

Used `groupby()` and `agg()` to calculate statistical values for each speed category.

Calculated:
- Average driving distance.
- Maximum driving distance.
- Minimum driving distance.
- Average speeding percentage.
- Maximum speeding percentage.
- Minimum speeding percentage.

```python
data.groupby(
    "speed_category",
    observed=True
).agg({
    "mean_dist_day": ["mean", "max", "min"],
    "mean_over_speed_perc": ["mean", "max", "min"]
})
```

### 9. Correlation Analysis

Used the `corr()` method to examine the relationship between average daily driving distance and speeding percentage.

```python
data[[
    "mean_dist_day",
    "mean_over_speed_perc"
]].corr()
```

### 10. Distance Categorization

Used NumPy's `where()` function to categorize drivers into High Distance and Low Distance groups.

```python
data["Distance_Category"] = np.where(
    data["mean_dist_day"] > 100,
    "High Distance",
    "Low Distance"
)
```

Used `value_counts()` and `unique()` to explore the distance categories.

## 📊 Analysis Performed

- Dataset exploration
- Duplicate removal
- Missing value checking
- Descriptive statistical analysis
- Sorting and filtering
- Speed percentage categorization
- Distance categorization
- Grouping and aggregation
- Correlation analysis
- Category distribution analysis

## 📚 Python Concepts Used

- Pandas DataFrame
- NumPy
- `head()` and `tail()`
- `describe()`
- `drop_duplicates()`
- `sort_values()`
- Conditional Filtering
- `pd.cut()`
- `value_counts()`
- `groupby()`
- `agg()`
- `corr()`
- `np.where()`
- `unique()`

## 🚀 Learning Outcomes

Through this project, I gained hands-on experience in Python programming, data cleaning, data manipulation, statistical analysis, grouping, aggregation, categorization, and extracting meaningful insights from driver data.

## 👩‍💻 Author

**Poornima G**

[GitHub Profile](https://github.com/poornimag2020)

---

⭐ If you find this project useful, feel free to explore the repository!
