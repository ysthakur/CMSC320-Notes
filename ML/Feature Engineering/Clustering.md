# Clustering

Why use clustering?
- If you want to find what classes are present in the data, you can use clustering and then manually review the clusters
- If you don't want to manually annotate your data, you can make a feature using clustering, then feed it to your model
- Can help find anomalies

## K-Means Clustering

K-means clustering is an unsupervised learning algorithm to assign each data point to a cluster

- $k$ is how many clusters you expect
- Tries to minimize the weighted distance between all points and the center of their assigned clusters
- The algorithm starts with randomly assigned centroids, then converges
    - At each step, each point is assigned to the closest centroid
    - The centers of each of these clusters become the new centroids
    - Repeat until it converges

[Visualization](https://www.naftaliharris.com/blog/visualizing-k-means-clustering/) of k-means clustering

Pros:
- Good when you want model to work with new data
	- With K-Means, you just find the closest centroid and add your new data point to that
	- With hierarchical clustering, if you get new data points, you need to perform clustering again

Cons:
- Assumes clusters are spherical and equally sized
	- Hierarchical clustering doesn't have this problem
	- However, can use modified version of k-means that clusters of different sizes and shapes

## Hierarchical Clustering

Two types:
- **Agglomerative** hierarchical clustering: Starts with individual nodes, then lumps them together into clusters
- **Divisive** hierarchical clustering: Starts with whole graph as one cluster, then divides it into smaller clusters

Pros:

- More likely to converge correctly
- Gives you a dendrogram, which gives you a more complete picture of the dataset

Cons:

- High time and space complexity
    - Cannot be used for large datasets
- No objective function for hierarchical clustering
- Sensitive to noise and outliers since we use distance metrics
- Difficulty handling large clusters
