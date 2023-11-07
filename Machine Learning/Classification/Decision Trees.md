---
tags:
  - classification
---

Supervised learning model

Very simple, not very good, outdated (but a building block of one of our strongest algorithms: [Random Forests](Random%20Forests.md))

> [!warning]
> Don’t use decision trees when you have an actual problem you want to solve

Use decision trees when:

- You want a pretty picture to show to someone
- You want a general sense of your data you can look at

## Training

Smaller is better:

- Fewer rules: more generalization
- Many rules: more specificity

We want to use as few rules as possible to classify our data

We want to get as possible to cutting the data in half with every split to get the smallest possible tree

So we want the splits with the most difference in information before and after the split

### Entropy

See sub-page: [Entropy](Entropy.md)

### Algorithm for picking a split

Start with all the data and no split

For each variable/dimension you can split on, compute the weighted information gain on splitting on that

## The Classification Algorithm

Steps to use a decision tree once you’ve trained it:

1. Get a piece of data with no label
2. Start at the top of the tree
3. Go down each branch based on the appropriate feature
4. When you get to a leaf, classify