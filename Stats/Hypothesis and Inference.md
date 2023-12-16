
Covered in 9/19 lecture

# Hypothesis Testing

Given a sample S from our population and a possible mean M, we can estimate the probability that we would see S if the true mean was M.

[Helpful article on hypothesis testing](https://www.scribbr.com/statistics/hypothesis-testing/)

## Vocab

- **Null hypothesis**: what you’re seeing doesn’t deviate from the population
- **Alternative hypothesis**: what you’re seeing is **different** from the population
- **p-value**: the probability that the null hypothesis is correct
    - Usually, p-value less than 0.05 is considered significant

## Statistical Hypothesis Tests

A **statistical hypothesis test** is a method of statistical inference used to decide whether the data at hand sufficiently support a particular hypothesis.

Most give you a p-value.

### Considerations when choosing statistical test

- What are you curious about? (mean, standard deviation, frequency)
- Is data categorical or continuous?
    - Categorical: chi square
- Do you have 1 or 2 samples?
- Do you have a large sample size and know the standard deviation of the population?
    - If large sample size (>30) *and* you know the standard deviation of the population, use z-test
    - If small sample size (<30) or you don’t know the standard deviation of the population, then use t-test
- Is data normally distributed?
    - If yes, use a parametric test (e.g. z-tests, t-tests, chi square)
    - If *very* non-normal, use non-parametric test (e.g. [Mann-Whitney U Test](<#Mann-Whitney U Test>))
- Is data paired? Is there a before and after?
    - If it is paired, can use a [paired t-test](<#Paired t-test>)

### One-sample t-test

Takes in a sample, tells you how likely it is the sample mean is the true mean

```python
from scipy import stats
stats.ttest_1samp(your_data, popmean=0.5)
```

Outputs a `TTestResult` containing a p-value (and other stuff)

### Two-sample t-test

You have 2 different groups and want to know if there’s a difference in the means of the two groups

### Paired t-test

Use case: You run a treatment and want to compare the before and after

- Null hypothesis: The means of both samples is the same
- Alternative hypothesis: The means of the two samples is not the same

### One-tailed t-test

A one-tailed t-test allows us to specify a *direction* (e.g. are men taller than women on average?)

- Null hypothesis: The difference between the means is either ≤0 or ≥0, depending on which direction you’re testing
- Alternate hypothesis: The difference between the means is either >0 or <0, depending on which direction you’re testing (opposite of the null hypothesis)

### Chi Square Test

Used for checking if 2 sets of categorical variables come from the same distribution

- Null hypothesis: The two samples come from the same distribution
- Alternative hypothesis: The two samples do not come from the same distribution

### One-way ANOVA Test

Use case: apply different treatments to different groups, check if difference between them

- Null hypothesis: There is no difference between any of the groups
- Alternative hypothesis: There is a difference between at least one of the groups

"One-way" means it has one independent variable

ANOVA tests assume the data is normal (parametric test)

### Mann-Whitney U Test

- Non-parametric test
- Used on ordinal or continuous data

### Dicky-Fuller Test

Used for checking if [time series](../Data%20Science/Time%20Series.md) are stationary. More info on the time series page

## Effect Size

Make sure to look at [effect size](Effect%20Size.md) in addition to statistical significance

## Errors

- Type 1 error: False positive (incorrectly reject a true null hypothesis)
- Type 2 error: False negative
