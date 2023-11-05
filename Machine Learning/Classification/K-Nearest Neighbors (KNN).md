---
tags:
  - instance-based
  - classification
---

**Supervised learning** model - training data has labels

Used for classification

## Weighted K-Nearest Neighbors

Closer neighbors have a stronger influence on the prediction since it’s weighted by distance

### Algorithm

1. Find the nearest $k$ points to our new data ($k$ is a hyperparameter here)
2. Take the weighted average of their labels based on their Euclidean distance
    - Could also use other kinds of distance (e.g. Manhattan distance, Hamming distance, cosine similarity), but Euclidean is most common
3. Assign that label

### Boundary conditions

- What if $k = 1$?
    - Model will just say whatever is closest
    - Will almost be memorizing things; won’t be able to generalize
- What if $k = n$?
    - Treats all points as neighbors
    - Soon, more and more irrelevant points will contribute, and we will just predict the mode of the data

### How to choose $k$

Try multiple $k$s and graph the error rate, pick the lowest

## Spherical K-Nearest Neighbors

You can also predefine sphere sizes and then let everything inside the sphere vote

Saves you the trouble of searching all the points

## Pros and Cons of K-Nearest Neighbors

Pros:

- Extremely accurate: used in large scale production in industry

Cons:

- Instance based model: Must be able to store the entire training set, which could be extremely large
- K must be tuned correctly
- Searching for the nearest neighbors is very time-consuming
    - Can be helped by the [spherical approach](K-Nearest%20Neighbors%20(KNN).md)