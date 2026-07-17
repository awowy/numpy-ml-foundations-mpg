# Vehicle Fuel Efficiency (MPG) Analysis: A GDGOC Foundation Project

This repository contains a comprehensive exploratory data analysis and mathematical modeling of the Seaborn MPG dataset. This project was developed for **GDGOC AI Module 2**, focusing on building machine learning foundations from scratch using **NumPy** and **Pandas**.

## Project Overview
The objective of this project is to analyze the factors influencing vehicle fuel efficiency (MPG). The analysis moves from data cleaning and statistical deep-dives to implementing advanced algorithms like **Linear Regression (Normal Equation)** and **Principal Component Analysis (PCA)** manually,.

## Key Features
*   **Manual Statistical Profiling:** Built a summary table for numeric features (Mean, Median, Std, IQR, and Outliers) using pure NumPy.
*   **Vectorized Data Processing:** Implemented Z-score standardization and correlation matrices without using high-level ML libraries.
*   **Advanced Visualizations:** Created distribution plots, origin comparisons, and correlation heatmaps to validate mathematical findings.
*   **Mathematical Foundations from Scratch:**
    *   **Normal Equation:** Solved $\hat{\theta} = (X^T X)^{-1} X^T y$ for linear regression.
    *   **PCA:** Reduced 5-dimensional engineering data into a 2D projection using eigen-decomposition,.
*   **Software Engineering:** Refactored the entire pipeline into a reusable `DatasetProfiler` class.

## The Implementation Journey (Learning Log)

*   **stage 1: data integrity and imputation**
    > i dscovered that the 'horsepower' column had 6 missing values. instead of dropping them, i chose median imputation to preserve the sample size of 398 rows while staying robust against outliers.
*   **stage 2: the physics of correlation**
    > manual correlation analysis showed that **weight** has a strong negative correlation of -0.83 with mpg,. i also found high multicollinearity between displacement, horsepower, and weight.
*   **stage 3: implementing math from scratch**
    > one of the hardesst parts was the normal equation. i learned that adding a 'bias' column of ones is essential for the intercept. for pca, i learned that mean-centering is non-negotiable to get the correct covariance matrix.
*   **stage 4: temporal engineering trends**
    > analyzing the data by decade showed a significant jump in fuel efficiency from the 1970s to the 1980s. this reflects real-world shifts in automotive engineering following the 1970s oil crisis.

## Technical Stack
*   **Language:** Python
*   **Data Science:** NumPy, Pandas
*   **Visualization:** Seaborn, Matplotlib
*   **AI Support:** Gemini (for documentation and debugging),

## How to Use
The project is modularized via the `DatasetProfiler` classs. You can run the entire analysis on the MPG dataset (or any other numeric dataset) with just a few lines:

```python
# initialize the profiler with the mpg dataset
profiler = DatasetProfiler(df, target_col='mpg')

# get stats using numpy-based calculations
# no pandas .describe() used here
print(profiler.summary_stats())

# generate the 4-panel dashboard
profiler.plot_dashboard(category_col='origin')

# get the final serialized report
print(profiler.generate_report())
```

---
*Developed as part of the GDGOC AI/ML Hands-On Series.*
