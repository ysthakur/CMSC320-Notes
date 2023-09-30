# Data Exploration

## Variable Relationships

- To look at correlations between variables, use `df.corr()`
  - This gives you Pearson's correlation coefficient
  - Will be 1 when variables are perfectly correlated
  - Will be -1 if perfectly anti-correlated
  - 0 otherwise

## Checking Seasonality

With all temporal data, always check for seasonal patterns (yearly, weekly, monthly)

## Identifying Errors

Look for:

- Duplicated values. Compare relative lengths of `len(df)` and `len(df.drop_duplicates())`
- Check for missing values. `sum(df["column"].isna())` will tell you how many missing values are in a series
- Check for outliers. These should show up in your box and whiskers chart
  - Make sure you understand why your outliers are outliers
