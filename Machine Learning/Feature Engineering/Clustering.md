## K-Means Clustering

K-means clustering is an unsupervised learning algorithm to assign each data point to a cluster

- $k$ is how many clusters you expect
- Tries to minimize the weighted distance between all points and the center of their assigned clusters
- The algorithm starts with randomly assigned centroids, then converges
    - At each step, each point is assigned to the closest centroid
    - The centers of each of these clusters become the new centroids
    - Repeat until it converges

[Visualization](https://www.naftaliharris.com/blog/visualizing-k-means-clustering/) of k-means clustering

## Hierarchical Clustering

Pros:

- More likely to converge correctly
- Gives you a dendrogram, which gives you a more complete picture of the dataset

Limits:

- High time and space complexity
    - Cannot be used for large datasets
- No objective function for hierarchical clustering
- Sensitive to noise and outliers since we use distance metrics
- Difficulty handling large clusters