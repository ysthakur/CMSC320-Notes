---
tags:
  - classification
---

> [!tip]
> Probably the most powerful classifier we have right now

- Creates N different decision trees, each trained on a subset of the data to avoid overfitting
- Each decision tree votes
- If a decision tree is overfit or has locked on to a weird correlation, it gets outvoted

Not great for super high-dimensional data