# Measures of Central Tendency in Statistics

This document covers the **measures of central tendency**—mean, mode, and median—in statistics, along with an explanation of skewed data and why the median is often a better choice than the mean when extreme values are present. These notes are beginner-friendly, with Python examples, for a Data Associate course.

## What are Measures of Central Tendency?

Measures of central tendency describe the "center" or typical value of a dataset. They help summarize data in a single number. The three main measures are:

### 1. Mean (Average)
- **Definition**: The sum of all values divided by the number of values.
- **Formula**: `mean = (x₁ + x₂ + ... + xₙ) / n`
- **Pros**: Uses every data point, good for symmetric data.
- **Cons**: Highly sensitive to extreme values (outliers).
- **Example**: `[1, 2, 3, 100]` → Mean = 26.5 (pulled up by 100).
- **Python**:
  ```python
  import numpy as np
  data = [1, 2, 3, 100]
  print("Mean:", np.mean(data))  # Output: 26.5
  ```

### 2. Median
- **Definition**: The middle value when data is sorted in ascending order.
- **Pros**: Not affected by extreme values, ideal for skewed data.
- **Cons**: Ignores the magnitude of most values.
- **Example**: `[1, 2, 3, 100]` → Median = 2.5 (middle of 2 and 3).
- **Python**:
  ```python
  import numpy as np
  data = [1, 2, 3, 100]
  print("Median:", np.median(data))  # Output: 2.5
  ```

### 3. Mode
- **Definition**: The most frequently occurring value in the dataset.
- **Pros**: Useful for categorical data or when frequency matters.
- **Cons**: May not exist (no repeats) or may not be unique (multiple modes).
- **Example**: `[1, 1, 2, 3]` → Mode = 1.
- **Python**:
  ```python
  import pandas as pd
  data = pd.Series([1, 1, 2, 3])
  print("Mode:", data.mode()[0])  # Output: 1
  ```

---

## Understanding Skewed Data

Skewness refers to the asymmetry of a dataset’s distribution. It affects which measure of central tendency is most representative.

### 1. Left-Skewed Data (Negative Skew)
- **Definition**: The left tail (lower values) is longer or fatter; most values are high, with a few unusually low outliers.
- **Examples**: 
  - Time to failure of machines (most last long, few fail early).
  - Age at death (most live long, few die young).
- **Effect**: Mean < Median < Mode.
- **Python Example**:
  ```python
  import matplotlib.pyplot as plt
  data = [10, 50, 60, 70, 80]  # Left-skewed
  plt.hist(data, bins=5, edgecolor='black')
  plt.show()
  print("Mean:", np.mean(data))  # 54
  print("Median:", np.median(data))  # 60
  ```

### 2. Right-Skewed Data (Positive Skew)
- **Definition**: The right tail (higher values) is longer or fatter; most values are low, with a few unusually high outliers.
- **Examples**: 
  - Income (most earn less, few earn a lot).
  - Time to repair a bug (most are quick, few take long).
- **Effect**: Mean > Median > Mode.
- **Python Example**:
  ```python
  data = [1, 2, 3, 4, 100]  # Right-skewed
  plt.hist(data, bins=5, edgecolor='black')
  plt.show()
  print("Mean:", np.mean(data))  # 22
  print("Median:", np.median(data))  # 3
  ```

---

## When to chose mean or median for measuring central tendency

For right-skewed data (e.g., income), the mean is higher than the median due to large outliers, so the median often better reflects the central tendency of the majority. For left-skewed data (e.g., time to failure), the mean is lower than the median, and again, the median may better represent the typical case.

## Handling Missing Data

Missing values can distort measures of central tendency. Here’s how to handle them:

- **Mean**: Use `np.nanmean()` to ignore missing values (NaN).
- **Median**: Use `np.nanmedian()` to compute the middle value, skipping NaN.
- **Mode**: Trickier; `pandas` can help, but check data first.
