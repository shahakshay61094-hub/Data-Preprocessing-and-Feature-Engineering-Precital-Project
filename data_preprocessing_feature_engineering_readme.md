# Data Preprocessing & Feature Engineering Project

# Complete Project Documentation

---

# Project Overview

This project demonstrates the complete workflow of:

- Data Loading
- Data Understanding
- Data Cleaning
- Missing Value Handling
- Outlier Handling
- Data Transformation
- Feature Scaling
- Feature Engineering
- Visualization
- Final Dataset Preparation

The project uses Python libraries like Pandas, NumPy, Scikit-learn, Matplotlib, and Seaborn.

---

# 1. Import Libraries

## Theory

Libraries are pre-written Python packages that help perform data analysis, preprocessing, visualization, and machine learning tasks.

---

## NumPy

```python
import numpy as np
```

### Purpose
- Numerical operations
- Mathematical calculations
- Arrays
- Statistics

---

## Pandas

```python
import pandas as pd
```

### Purpose
- Data handling
- Data cleaning
- Reading CSV/JSON/SQL
- Data transformation

---

## Matplotlib

```python
import matplotlib.pyplot as plt
```

### Purpose
Used for data visualization.

### Graphs
- Histogram
- Line chart
- Bar chart
- Scatter plot

---

## Seaborn

```python
import seaborn as sns
```

### Purpose
Advanced visualization library.

### Used For
- Heatmaps
- Boxplots
- Distribution plots

---

## SimpleImputer

```python
from sklearn.impute import SimpleImputer
```

### Purpose
Fills missing values.

### Strategies
- Mean
- Median
- Most Frequent

---

## KNNImputer

```python
from sklearn.impute import KNNImputer
```

### Purpose
Predicts missing values using nearest neighbors.

---

## Encoding Libraries

```python
LabelEncoder
OneHotEncoder
OrdinalEncoder
```

### Purpose
Convert categorical data into numerical format.

Machine learning models only understand numbers.

---

## Scaling Libraries

```python
StandardScaler
MinMaxScaler
```

### Purpose
Scale features into similar range.

---

# 2. Data Loading

## Theory

Data loading means importing data from different sources into Python.

---

## CSV Loading

```python
pd.read_csv()
```

### CSV
Comma Separated Values.

---

## JSON Loading

```python
pd.read_json()
```

### JSON
JavaScript Object Notation.

Mostly used in APIs and web applications.

---

## SQL Loading

```python
pd.read_sql()
```

### Purpose
Load data from SQL databases.

---

# 3. Data Understanding

## Theory

Before cleaning data, we understand:

- Shape
- Columns
- Data types
- Missing values
- Duplicate records

This process is called Data Understanding.

---

## head()

```python
df.head()
```

Shows top 5 records.

---

## tail()

```python
df.tail()
```

Shows last 5 records.

---

## shape

```python
df.shape
```

Returns:

```python
(rows, columns)
```

Example:

```python
(1000, 15)
```

---

## columns

```python
df.columns
```

Displays all column names.

---

## dtypes

```python
df.dtypes
```

Displays datatypes.

### Common Types
- int
- float
- object
- datetime

---

## info()

```python
df.info()
```

Provides:

- Column names
- Datatypes
- Missing values
- Memory usage

---

## describe()

```python
df.describe()
```

Provides statistical summary.

Includes:

- Mean
- Median
- Standard deviation
- Minimum value
- Maximum value

---

# 4. Data Cleaning

## Theory

Data cleaning means fixing bad-quality data.

Problems include:

- Missing values
- Duplicates
- Invalid values
- Wrong formats

---

## Duplicate Removal

```python
df.drop_duplicates()
```

### Purpose
Removes repeated rows.

---

## Fix Invalid Values

### Example
Negative price values.

```python
-500
```

Price cannot be negative.

Solution:

```python
abs()
```

---

## Date Conversion

```python
pd.to_datetime()
```

### Purpose
Converts dates into proper datetime format.

---

# Missing Value Handling

## Theory

Missing values are empty or null values.

Example:

```python
NaN
```

---

## Numerical Imputation

```python
strategy='mean'
```

### Formula

Mean = Sum of values / Total values

### Purpose
Fill missing numerical values using average.

---

## Categorical Imputation

```python
strategy='most_frequent'
```

### Purpose
Fill missing categorical values using most repeated category.

---

## KNN Imputer

### Theory

KNN means K-Nearest Neighbors.

It predicts missing values using similar rows.

---

# 5. Outlier Handling

## Theory

Outliers are abnormal extreme values.

Example:

- Normal salary = 50,000
- Outlier salary = 10,00,00,000

---

## Z-Score Method

### Formula

```python
z = (x - mean) / standard deviation
```

### Rule

```python
z > 3
```

Then value is considered an outlier.

---

## IQR Method

### Formula

```python
IQR = Q3 - Q1
```

### Lower Bound

```python
Q1 - 1.5 * IQR
```

### Upper Bound

```python
Q3 + 1.5 * IQR
```

---

## Winsorization

### Theory

Instead of deleting outliers, we cap them.

Example:

```python
1000000 -> 50000
```

---

# 6. Data Transformation

## Theory

Data transformation converts data into better format for machine learning.

---

## Date Feature Extraction

Extract:

- Day
- Month
- Year

### Benefit
Helps models understand time patterns.

---

## Label Encoding

### Theory

Converts binary categories into numbers.

Example:

```python
Male = 1
Female = 0
```

---

## One Hot Encoding

### Theory

Creates separate columns for categories.

Example:

| City |
|------|
| Rajkot |
| Surat |

Becomes:

| City_Rajkot | City_Surat |

---

## Ordinal Encoding

### Theory

Used when categories have order.

Example:

```python
Low < Medium < High
```

Converted as:

```python
Low = 0
Medium = 1
High = 2
```

---

## Binning

### Theory

Converts continuous values into groups.

Example:

```python
Income -> Low / Medium / High
```

---

## Log Transformation

### Formula

```python
y = log(1+x)
```

### Purpose
Reduces skewness.

---

## Square Root Transformation

### Formula

```python
y = √x
```

### Purpose
Mild skewness reduction.

---

# 7. Feature Scaling

## Theory

Scaling brings all features into similar range.

---

## StandardScaler

### Formula

```python
z = (x - mean) / standard deviation
```

### Output
- Mean = 0
- Standard deviation = 1

---

## MinMaxScaler

### Formula

```python
(x - min) / (max - min)
```

### Output Range

```python
0 to 1
```

---

## ColumnTransformer

### Purpose
Apply multiple preprocessing operations together.

---

# 8. Feature Construction

## Theory

Feature construction means creating new useful features from existing data.

This improves model performance.

---

## Average Monthly Spend

### Formula

```python
Total Spend / 12
```

### Purpose
Find monthly spending behavior.

---

## Purchase Frequency

### Formula

```python
Purchase Count / 30
```

### Purpose
Measure customer activity.

---

## Days Since Last Purchase

### Formula

```python
Current Date - Last Purchase Date
```

### Purpose
Find inactive customers.

---

## Category Wise Total Expenditure

### Purpose
Find which category generates maximum revenue.

---

# Final Dataset Preparation

## Theory

After preprocessing:

- Final cleaned dataset is created
- Saved into CSV file

---

# Pandas Profiling

## Theory

Automatically generates:

- EDA report
- Correlation report
- Missing value report
- Distribution analysis

---

# Visualization

## Histogram

### Purpose
Shows data distribution.

---

## Boxplot

### Purpose
Detect outliers visually.

---

## Heatmap

### Purpose
Shows correlation between features.

---

# Final Conclusion

This project covers:

- Data Loading
- Data Understanding
- Data Cleaning
- Missing Value Handling
- Outlier Handling
- Data Transformation
- Encoding
- Feature Scaling
- Feature Engineering
- Visualization
- Final Dataset Preparation

This is a complete Data Preprocessing & Feature Engineering workflow used in real-world Data Science and Machine Learning projects.

