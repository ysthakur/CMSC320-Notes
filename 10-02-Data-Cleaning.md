# Data Cleaning

## Common errors

- If data is in wrong format:
  - Can sometimes use `df["column"].astype(<some type>)`
  - Otherwise, can use `df["column"].apply(...)`
- If labels change midway through the data, can do one of these:
  - Divide the dataset in two
  - Infer old ratings
- Duplicates (**always check for duplicates**)
  - If exact duplicates, do `df.drop_duplicates()`
  - If some of them are subtly different, identify the ones that are the correct values and drop the rest

## Outlier detection

Use **z-score** for detecting outliers: `z = (x - mean(sample)) / stddev(sample)`.
The z-score of a point is basically how many standard deviations it's away from the mean

## Missing Data

Data could be missing at random or not

### Data missing at random:

- No pattern
- If data is categorical, then you could just make "Missing" a category
- If data is numerical:
  - If it's a very small portion of your data, you can just drop it (`df.dropna()`)
    - **Can only do this if data missing at random**
  - Otherwise, can use **imputation**
    - Mean imputation: fill in missing values with mean
    - Mode imputation: fill in missing values with most common value
    - Hot-deck imputation: find row most similar to the row with a missing value, then copy the value from that row
    - Bayesian imputation: fill in with most likely value (probably won't have to use this? Max never has)

### Data not missing at random:

- Either one particular value or one particular range is more likely to be missing

