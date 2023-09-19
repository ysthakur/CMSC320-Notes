# Hypothesis Testing

Given a sample S from our population and a possible mean M, we can estimate
the probability that we would see S if the true mean was M.

## Vocab

- **Null hypothesis**: what you're seeing doesn't deviate from the population
- **Alternative hypothesis**: what you're seeing is **different** from the population
- **p-value**: the probability that the null hypothesis is correct
  - Usually, p-value less than 0.05 is considered significant

## Statistical Hypothesis Tests

A **statistical hypothesis test** is a method of statistical inference used to decide
whether the data at hand sufficiently support a particular hypothesis.

Most give you a p-value.

### Considerations when choosing statistical test

- What are you curious about? (mean, standard deviation, frequency)
- Is data categorial or continuous?
- Do you have 1 or 2 samples?
- Is data normally distributed?
  - If yes, use a parametric test
  - If *very* non-normal, use non-parametric test
- Is data paired? Is there a before and after?

### One-sample t-test

Takes in a sample, tells you how likely it is the sample mean is the true mean

```python
import numpy as np
from scipy import stats
stats.ttest_1samp(your_data, popmean=0.5)
```

Outputs a `TTestResult` containing a p-value (and other stuff)

### Two-sample t-test

- You have 2 different groups and want to know if there's a different in the means
  of the two groups

### Paired t-test

- Use case: You run a treatment and want to compare the before and after

### One-tailed t-test

A one-tailed t-test allows us to specify a *direction*

### Chi Square Test

Used for checking if 2 sets of categorical variables come from the same distribution

- Null hypothesis:
- Alternative hypothesis:

### One-way Anova Test

Use case: Apply different treatments to different groups, check if difference between them

- Null hypothesis: There is no difference between any of the groups
- Alternative hypothesis: There is a difference between at least one of the groups

## Errors

- Type 1 error: False positive (incorrectly reject a true null hypothesis)
- Type 2 error: False negative
