---
tags:
  - classification
---

Supervised learning model

Very simple, not very good, outdated (but a building block of one of our strongest algorithms: [Random Forests](<Random Forests.md>))

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

- Deep trees are bad (deep = lots of levels, rules)
- Bushy trees are fine (bushy = lots of splits at a single level)

### Entropy

See sub-page: [Entropy](Entropy.md)


### Algorithm for picking a split

- We want to get as possible to cutting the data in half with every split to get the smallest possible tree
- So we want the splits with the most **difference** in information before and after the split
- If you had 1 bit of entropy before the split and have 0.97 bits of entropy after the split, your information gain is only 0.03
	- You want to have an information gain of 1 (start with 1 bit of entropy, and have 0 bits of entropy after split)
- Splits can cause different sizes, e.g. you go from 1 bit of entropy to 0 bits of entropy for one child node but 0.99 bits of entropy for the other child node
	- So information gain needs to be the weighted sum of each branch

Use a greedy heuristic:
- Start with all the data and no split
- For each column you can split on, compute the weighted information gain on splitting on that
	- Find the column with the most information gain
- Repeat until you have no entropy left

### Math for the algorithm

$$H(\text{Node}) = \sum p \lg\left(\frac 1 p\right)$$
Weighted entropy:
$$H(\text{Split}) = \frac{\text{size}_{right} \cdot H(\text{right}) + \text{size}_{left} \cdot H(\text{left})}{\text{size}_{right} + \text{size}_{left}}$$
Information gain is $$H(\text{Before split}) - H(\text{After split})$$

## The Classification Algorithm

Steps to use a decision tree once you’ve trained it:

1. Get a piece of data with no label
2. Start at the top of the tree
3. Go down each branch based on the appropriate feature
4. When you get to a leaf, classify