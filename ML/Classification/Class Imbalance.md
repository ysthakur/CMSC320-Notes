---
tags:
  - classification
---
Big problem for classifiers

Happens when an overwhelming majority of your data is a single class

Examples of class imbalance:

- Fraud - Most transactions aren’t fraudulent
- Disease - Most people won’t have the disease
- Product - Most people won’t buy any given product

It's very common to have a rare **positive signal** surrounded by negatives

Options for dealing with class imbalance:

- Use `class_weight` parameter in sklearn
- Create multiple examples of your negative features with slight differences
- Equalize your training set
