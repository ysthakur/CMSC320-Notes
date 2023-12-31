
Covered in 9/12 lecture

Conditional probability: $P(A \mid B) = \frac{P(A \cap B)}{P(B)}$

Bayes rule: $P(A \mid B) = \frac{P(B \mid A) \cdot P(A)}{P(B)}$

Expected value: $E[X] = \sum (x_i \cdot p(x_i))$ where $x_i$ is the values that $X$ takes and $p(x_i)$ is the probability that $X$ takes the value $x_i$.

## Distributions

- A distribution is a statistical function that gives the probability of a given outcome from an experiment
- Continuous, but large enough sample size converges to the right thing
- Distributions are like histograms

Types:

- Uniform distribution
    - Just a horizontal line
- Normal distribution (Gaussian)
    - Extremely common, often assume normal distribution unless reason to think otherwise
    - Continuous
- Poisson distribution
    - Sums to 1, scrunched up on one side
    - Given the rate of some event occurring, poisson distribution tells you probability of the number of occurrences over a time period
    - Discrete
- Zero-inflated poisson distribution
    - Poisson distribution with a spike at 0
- Bernoulli distribution
    - When you just have one thing with that has a set probability of happening
    - Example: Flipping a coin once
- Binomial distribution
    - The probability of getting a set of outcomes from a set of Bernoulli Trials
    - Discrete
    - Looks like a normal distribution (if you have enough trials)
- Power law distribution
    - e.g. number of close friends

## [Central Limit Theorem](Central%20Limit%20Theorem.md)

![[Central Limit Theorem]]

## Summary Statistics

- Examples: Mean, median, mode
- Cannot rely solely on summary statistics, need to first understand your data holistically

Measures of central tendency:

- The Pythagorean means
    - Arithmetic mean - Very sensitive to outliers
    - Geometric mean - A measure of central tendency less sensitive to outliers
    - Harmonic mean - Primarily used for rates (we won’t use it)
- Median
- Mode

Measures of variance:

- Variance: $s^2$
- Standard deviation: $s = \sqrt{\frac{\sum (x_i-\bar{x})^2}{n-1}}$

Other descriptors:

- Skew (left- or right-tailed): Whether distribution is shifted to left or right
    - Negative skew: Mean is shifted to right
    - Positive skew: Mean is shifted to left
- Modality: How the modes are distributed (e.g. unimodal, bimodial, etc.)