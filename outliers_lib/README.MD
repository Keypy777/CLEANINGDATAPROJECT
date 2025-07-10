# Data Cleaning and Analysis Project

This project demonstrates a comprehensive approach to cleaning and analyzing real-world tabular data using Python and pandas. The dataset used is `sber_data.csv`, which contains information about real estate in Moscow.

## Step-by-Step Process

### 1. Data Loading and Initial Exploration

- Loaded the dataset using `pd.read_csv`.
- Explored the data with `.head()`, `.tail()`, and `.info()` to understand its structure, types, and missing values.
- Used `value_counts()` to inspect categorical features.

### 2. Visual Data Exploration

- Plotted boxplots and scatterplots to visualize relationships between features (e.g., price vs. ecology, price vs. distance to Kremlin).
- Used seaborn and matplotlib for visualization.

### 3. Handling Missing Values

- Identified missing values using `.isnull()` and calculated the percentage of missing data per column.
- Visualized missing data distribution with bar plots and heatmaps for better understanding.

#### Strategies for Handling Missing Data:

- **Column Removal:** Removed columns with more than 30-40% missing values, as they are unlikely to be informative.
- **Row Removal:** For columns with few missing values, removed rows containing missing data to preserve important features.
- **Imputation:** Filled missing values using:
  - Median for continuous features with skewed distributions.
  - Mode for discrete or categorical features.
  - Logical imputation (e.g., filling `life_sq` with `full_sq` if missing).
- **Indicator Features:** Added boolean columns to indicate where missing values were imputed, helping models recognize imputed data.

### 4. Outlier Detection and Removal

- Used descriptive statistics and visualizations (histograms, boxplots) to spot anomalies.
- Applied the Tukey method (IQR) and z-score method (with optional log transformation) to systematically detect outliers.
- Removed or flagged outliers based on domain knowledge and statistical thresholds.

### 5. Duplicate Detection and Removal

- Checked for duplicate rows (excluding unique identifiers) using `.duplicated()`.
- Removed full duplicates with `.drop_duplicates()` to ensure data integrity.

### 6. Identifying and Removing Low-Information Features

- Calculated the proportion of the most frequent value and the ratio of unique values for each column.
- Flagged columns as low-information if:
  - More than 95% of values are identical, or
  - More than 95% of values are unique.
- Removed these columns to reduce dimensionality and avoid the curse of dimensionality.

### 7. Summary

- The cleaned dataset is free from excessive missing values, outliers, duplicates, and non-informative features.
- Each cleaning step is justified by data analysis and visual inspection.
- The resulting data is ready for further modeling and analysis.

---

## How to Run

1. Place `sber_data.csv` in the `data_clean/` directory.
2. Open and run [datacleaningexample.ipynb](skillfactory_advanced_data/DATACLEANINGPROJECT/datacleaningexample.ipynb) in Jupyter or VS Code.
3. Follow the notebook cells for detailed explanations and code.

---

## Key Libraries Used

- pandas
- numpy
- matplotlib
- seaborn

---

This project provides a practical template for robust data cleaning and exploratory analysis, ensuring high-quality data for downstream machine learning tasks.