#unsupervised-learning 

Two types:
- **Agglomerative** hierarchical clustering: Starts with individual nodes, then lumps them together into clusters
- **Divisive** hierarchical clustering: Starts with whole graph as one cluster, then divides it into smaller clusters

Pros:

- More likely to converge correctly than [K-Means Clustering](ML/Feature%20Engineering/K-Means%20Clustering.md)
- Gives you a dendrogram, which gives you a more complete picture of the dataset

Cons:

- High time and space complexity
    - Cannot be used for large datasets
- No objective function for hierarchical clustering
- Sensitive to noise and outliers since we use distance metrics
- Difficulty handling large clusters
