#unsupervised-learning


K-means clustering is an unsupervised learning algorithm to assign each data point to a cluster

- $k$ is how many clusters you expect
- Tries to minimize the weighted distance between all points and the center of their assigned clusters
- The algorithm starts with randomly assigned centroids, then converges
    - At each step, each point is assigned to the closest centroid
    - The centers of each of these clusters become the new centroids
    - Repeat until it converges

[Visualization](https://www.naftaliharris.com/blog/visualizing-k-means-clustering/) of k-means clustering

## Pros and Cons

Pros:
- Good when you want model to work with new data
	- With K-Means, you just find the closest centroid and add your new data point to that
	- With hierarchical clustering, if you get new data points, you need to perform clustering again

Cons:
- Assumes clusters are spherical and equally sized
	- Hierarchical clustering doesn't have this problem
	- However, can use modified version of k-means that clusters of different sizes and shapes

## Choosing a K

- Try a bunch of different Ks
- For each K, calculate its Within-Cluster Sum of Square (WCSS)
- WCSS = sum of squares of the distances between each data point in the cluster to the centroid
- As K increases, WCSS will decrease
- But the "elbow" of this graph is where the optimal K will be
