---
aliases: []
---
Covered in lecture 10/17 (?)

[Slides](https://docs.google.com/presentation/d/1zE54CPwDybdcAziepPob7hqC_aEEogAfsD7wZKLn-m0/edit#slide=id.g2848ac0f2f8_0_203)

Feature engineering is the creation or modification of columns to make life easier for us or our machine learning models

Generally, mathematical models:

- Don’t like categorical data
- Don’t do super well with columns that have different scales
- Are fussy in lots of other ways

## Transforms

Creating a new column by applying a function over a column

Transforms can be **linear** or **non-linear**

### Normalization

$$x_{scaled} = \frac{x - x_{min}}{x_{max} - x_{min}}$$

### Standardization

Just get z-scores.
We apply this formula and set the mean to 0 and standard deviation to 1:

$$z = \frac{x_i - \mu}{\sigma}$$

### Log Transforms

> [!tip]
> Use log transform to convert a power law distribution into a more normal distribution

The base doesn't matter

## One Hot Encoding

[One Hot Encoding](<One Hot Encoding.md>)

## Binning

![Binning](Binning.md)

## Clustering

[Clustering](Clustering.md)

## Dimensionality Reduction

Sometimes we have too many dimensions and need to get rid of some

If you have obviously irrelevant variables, you can just remove those, but not always that easy

Enter [PCA](PCA.md)