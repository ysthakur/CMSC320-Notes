---
tags:
  - classification
---
Finds hyperplane in n-dimensional space that divides the data into the desired classes

Specifically finds the hyperplane with the **maximal margin** (maximum distance between data points of both classes)
- Maximizes margin to create wider gap between the different classes so it'll work better on new data

**Support vectors**: Closest data points to the hyperplane
- Critical role in deciding the hyperplane and margin

If data is not linearly separable, uses cool math to introduce new dimensions that slice the data (kernel)

Has multiple hyperparameters:
- alpha
- C: Regularization parameter, inversely proportional to regularization strength
- Kernel: Mathematical method to transform data into higher-dimensional space
	- Linear kernel SVMs do well with high dimensional data