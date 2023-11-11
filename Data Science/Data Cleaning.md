
Covered in lecture on 9/28 and 10/3

## Common Errors

- If data is in wrong format:
    - Can sometimes use `df["column"].astype(<some type>)`
    - Otherwise, can use `df["column"].apply(...)`
- If labels change midway through the data, can do one of these:
    - Divide the dataset in two
    - Infer old ratings

## Duplicates

> [!warning]
> Always check for duplicates

- Can detect duplicates by comparing relative lengths of `len(df)` and `len(df.drop_duplicates())`
- If exact duplicates, do `df.drop_duplicates()`
- If some of them are subtly different, identify the ones that are the correct values and drop the rest

## Outlier Detection

You can use a box and whiskers chart to spot outliers

Use **z-score** for detecting outliers:

$$Z = \frac{x - \mu}{\sigma}$$

where $x$ is the observed value, $\mu$ is the mean of the sample, and $\sigma$ is the standard deviation of the sample

The z-score of a point is basically how many standard deviations it's away from the mean

Make sure you understand *why* your outliers are outliers

## Missing Data

Check for missing values. `sum(df["column"].isna())` will tell you how many missing values are in a series

Data could be missing at random or not

### Data missing at random

- No pattern
- If data is categorical, then you could just make “Missing” a category
- If data is numerical:
    - If it’s a very small portion of your data, can just drop it (`df.dropna()`)
        
        <aside>
        ⚠️ Can only do this if data missing at random
        
        </aside>
        
    - Otherwise, can use **imputation**:
        - Mean imputation: fill in missing values with mean
        - Mode imputation: fill in missing values with most common value
        - Hot-deck imputation: find row most similar to the row with a missing value, then copy the value from that row
        - Bayesian imputation: fill in with most likely value (probably won't have to use this? Max never has)

### Data not missing at random

Possible ways for data to be missing not at random:

- One particular value is missing
- One particular range of rows missing
    - If you lost rows in the middle of your data, it might still be possible to do imputation
- Boundary conditions: e.g. birds flew out of sensor range or Geiger counter only goes up to a certain value
    
    **Cannot do imputations with boundary conditions**
    
    Possible ways to deal with boundary conditions:
    
    - Drop everything outside, only work with stuff within boundary
    - Extrapolate the same distribution outside the boundary
    - Get more data

## Incorrect Data

Types of incorrect data:

- People lied to you
- Faulty instrumentation
    - To repair, you can look at past sensor data (or a similar sensor) and adjust distribution to be closer to the past one
    - Only works if you understand what sort of error you have
- You’ve been recording the wrong metrics
- Two identical entries with different values
- Illegal values
- Unclear default values

### Detecting Incorrect Data

- If there’s a discontinuity, it might be because people round when self-reporting
    - Max called it an **attractor**
    - Takes advanced statistics to normalize - can “smooth out” by taking the spike and spreading it down the curve
    - e.g. someone who’s 5’11 or 6’1 might say they’re 6 feet because it’s nice and round
    - e.g. people underreporting their income so they can get a scholarship, resulting in a spike before the scholarship threshold on one side
- Modes that don’t make sense (e.g. latitude/longitude 0, 0)
- Data outside valid bounds (e.g. someone playing a video game for a million hours)
- Signs of boundary conditions - Your data has a discontinuity at a certain value, after which there is nothing