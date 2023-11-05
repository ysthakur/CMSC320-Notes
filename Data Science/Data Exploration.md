
Covered in 9/28 lecture

## Exploratory Data Analysis (EDA)

[Fardina’s Colab](https://colab.research.google.com/drive/11JjW055RQ-poNCXTlzPiUxgs9hMi5Xns?usp=sharing)

EDA is about looking at and understanding your data before doing stuff with it so that you can:

- Discover patterns
- Spot anomalies
- Test hypotheses
- Check assumptions using summary statistics and graphical representations

Possible steps:

- First, you want to see how variables are distributed
  - Can use box plots, histograms, etc.
  - `hist()` can generate a histogram of a `Series`
  - [[Data Visualization]]
- A scatterplot can help by:
  - Visualizing relationships
  - Showing outliers
- Correlation analysis (using [[Pearson's Correlation Coefficient]])
- Use statistical tests to check if two datasets with different averages come from the same distribution ([[Hypothesis and Inference]])

## Checking Seasonality

With all temporal data, always check for seasonal patterns (yearly, weekly, monthly)

## Identifying Errors

Look for:

- Duplicates: [Duplicates](Data%20Cleaning.md)
- Missing values: [Missing Data](Data%20Cleaning.md)
- Outliers: [Outlier Detection](Data%20Cleaning.md)