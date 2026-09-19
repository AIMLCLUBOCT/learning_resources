# Module 03: Data Science & Exploratory Data Analysis

> Transform messy real-world datasets into actionable intelligence using Pandas, Matplotlib, and Seaborn.

---

## 📋 Prerequisites
- Module 01 (Python & NumPy).
- Module 02 (Descriptive Statistics).

---

## 🧠 Core Concepts

1. **Tabular Data Wrangling with Pandas:**
   - Data structures: `Series` (1D) and `DataFrame` (2D).
   - Indexing and selecting: `.loc[]` (label-based) vs. `.iloc[]` (integer-based).
   - Data types, type casting (`.astype()`), and memory optimization.
2. **Data Cleaning & Preprocessing:**
   - Detecting and handling missing data (`isna()`, `dropna()`, `fillna()` with mean/median/mode).
   - Removing duplicate records (`drop_duplicates()`).
   - Outlier detection: Z-score and Interquartile Range (IQR) method.
3. **Aggregations & Reshaping:**
   - Grouping operations: `.groupby()`, `.agg()`, pivot tables.
   - Merging, joining, and concatenating DataFrames (`pd.merge`, `pd.concat`).
4. **Exploratory Data Analysis (EDA) & Visualization:**
   - Distribution plots: Histograms, KDE plots.
   - Relationship plots: Scatter plots, pair plots.
   - Categorical plots: Box plots, violin plots, bar charts.
   - Correlation analysis: Pearson correlation matrix and heatmaps.
5. **Feature Engineering:**
   - Handling categorical features: One-Hot Encoding (`pd.get_dummies`), Ordinal Encoding.
   - Numerical feature scaling: Standardization (Z-score normalization) vs. Min-Max Scaling.

---

## 🗺️ Recommended Sequence

1. Work through the [Pandas User Guide](https://pandas.pydata.org/docs/user_guide/index.html).
2. Complete the free [Kaggle Learn: Pandas](https://www.kaggle.com/learn/pandas) course.
3. Complete the [Kaggle Learn: Data Visualization](https://www.kaggle.com/learn/data-visualization) course.
4. Practice performing an EDA on the classic Titanic or California Housing dataset.

---

## 💻 Practical Exercises

### Exercise: Complete Exploratory Pipeline
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# 1. Load sample dataset
df = sns.load_dataset('titanic')

# 2. Inspect missingness
print("Missing values per column:\n", df.isna().sum())

# 3. Clean: Impute missing age with median
df['age'] = df['age'].fillna(df['age'].median())

# 4. Group by survival and passenger class
survival_rates = df.groupby('pclass')['survived'].mean()
print("\nSurvival rate by class:\n", survival_rates)

# 5. Visual summary: Boxplot of fare by class
plt.figure(figsize=(8, 4))
sns.boxplot(data=df, x='pclass', y='fare', showfliers=False)
plt.title("Fare Distribution by Passenger Class")
plt.show()
```

---

## 💡 Project Ideas
- **E-Commerce Customer EDA:** Analyze customer transaction records to identify top spending categories, churn signals, and purchase distributions.
- **Air Quality & Weather Analysis:** Ingest local Bhopal / MP meteorological data, clean missing sensor readings, and visualize seasonal pollution trends.

---

## 📖 Official Documentation & Resources
- 📖 [Pandas Documentation](https://pandas.pydata.org/docs/)
- 📖 [Matplotlib User Guide](https://matplotlib.org/stable/users/index.html)
- 📖 [Seaborn Documentation](https://seaborn.pydata.org/)
- 🎓 [Kaggle Learn: Pandas & Data Cleaning](https://www.kaggle.com/learn)
