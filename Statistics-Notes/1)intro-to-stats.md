# Introduction to Statistics

This document serves as a beginner-friendly guide to statistics, tailored for a Data Associate course with a focus on Python. It covers the basics of statistics, types of data, measurement scales, and practical examples—all from A to Z.

## What is Statistics?

Statistics is the discipline of collecting, organizing, analyzing, interpreting, and presenting data to uncover patterns, trends, and insights for decision-making.

### Key Branches of Statistics
1. **Descriptive Statistics**: Summarizes and describes data using measures like mean, median, and mode.
   - Example: Average age of Python developers in a dataset.
2. **Inferential Statistics**: Makes predictions or generalizations about a population based on a sample.
   - Example: Predicting user satisfaction based on survey results.

### Importance
- Drives data science tasks (e.g., analyzing GitHub commit trends).
- Supports decision-making (e.g., optimizing code performance).

---

## Types of Data

Data is classified by its nature and how it’s measured. Here’s a breakdown:

### 1. Categorical Data (Qualitative)
- **Definition**: Non-numeric data representing categories or qualities.
- **Examples**: 
  - Programming languages (Python, Java, C++)
  - User feedback (Positive, Neutral, Negative)
- **Subtypes**:
  - **Nominal**: No inherent order (e.g., eye color: Blue, Brown, Green, married/unmarried ,country of residence).
  - **Ordinal**: Ordered categories (e.g., skill level: Beginner, Intermediate, Advanced).
- **Python Example**:
  ```python
  import pandas as pd
  categories = pd.Series(['Python', 'Java', 'C++'], dtype='category')
  print(categories)
  ```

### 2. Numerical Data (Quantitative)
- **Definition**: Numeric data representing measurable quantities.
- **Examples**: 
  - Lines of code written (500)
  - Time to execute a script (3.14 seconds)
- **Subtypes**:
  - **Discrete**: Countable whole numbers (e.g., number of bugs in a program).
  - **Continuous**: Any value within a range (e.g., CPU temperature in °C).
- **Python Example**:
  ```python
  import numpy as np
  discrete = [5, 10, 15]  # Bug counts
  continuous = [2.5, 3.1, 4.7]  # Run times
  print("Discrete Mean:", np.mean(discrete))
  print("Continuous Mean:", np.mean(continuous))
  ```

---

## Measurement Scales

Data types align with measurement scales, which dictate applicable statistical methods:

1. **Nominal Scale**
   - Unordered categories.
   - Example: Operating systems (Windows, macOS, Linux).
   - Stats: Mode.
   - Python: `pd.Series(['Windows', 'Linux']).mode()`.

2. **Ordinal Scale**
   - Ordered categories, unequal intervals.
   - Example: Course difficulty (Easy, Medium, Hard).
   - Stats: Median.
   - Python: `pd.Series(['Easy', 'Hard', 'Medium']).sort_values()`.

3. **Interval Scale**
   - Equal intervals, no true zero.
   - Example: Temperature in Fahrenheit.
   - Stats: Mean, standard deviation.
   - Python: `np.mean([32, 68, 104])`.

4. **Ratio Scale**
   - Equal intervals, true zero.
   - Example: Distance in kilometers.
   - Stats: All (mean, ratios, etc.).
   - Python: `np.mean([0, 5, 10])`.

---

## Core Statistical Concepts

### A. Descriptive Statistics
- Tools to summarize data.
- Examples: Mean (average), Median (middle value), Mode (most common).
- Python: `np.mean()`, `np.median()`, `pd.Series.mode()`.

### B. Inferential Statistics
- Tools to infer insights about a population from a sample.
- Examples: Hypothesis testing, confidence intervals.
- Python: Use `scipy.stats` for t-tests or predictions.

### C. Population vs. Sample
- **Population**: All items of interest (e.g., all Data Associate students).
- **Sample**: A subset (e.g., 50 students surveyed).
- Python: `random.sample(range(100), 10)`.

### D. Variables
- **Independent**: Causes change (e.g., study hours).
- **Dependent**: Affected by change (e.g., test scores).

### E. Measures of Central Tendency
- Mean: `np.mean([1, 2, 3])` → 2.
- Median: `np.median([1, 2, 3])` → 2.
- Mode: `pd.Series([1, 1, 2]).mode()` → 1.

### F. Measures of Dispersion
- Range: `max([1, 5]) - min([1, 5])` → 4.
- Variance: `np.var([1, 2, 3])`.
- Standard Deviation: `np.std([1, 2, 3])`.

---

## Detailed Data Types Breakdown

1. **Numerical Data**
   - Measurable, numeric values.
   - Includes Discrete and Continuous.

2. **Categorical Data**
   - Non-numeric, descriptive.
   - Includes Nominal and Ordinal.

3. **Continuous Data**
   - Infinite possible values in a range.
   - Example: Height (175.3 cm).

4. **Discrete Data**
   - Finite, countable values.
   - Example: Number of commits (42).

5. **Nominal Data**
   - Unordered categories.
   - Example: City names (New York, Tokyo).

6. **Ordinal Data**
   - Ordered categories.
   - Example: T-shirt sizes (S, M, L).
