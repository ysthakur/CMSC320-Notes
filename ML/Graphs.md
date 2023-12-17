Graphs as in graph theory

## Graph Problems

Graph level tasks:
- Describe properties of a graph
- Predict how graph will behave
- Find clusters/structure within graph
- Describe change over time

Node level tasks:
- Classify nodes based on community

Edge level tasks:
- Predict when an edge will form
- Identify anomalous edges

## Vocabulary

- In-degree/out-degree: Incoming and outgoing edges, respectively
- Temporal graphs:
	- Edges can be added over time
	- Nodes and edges can be added over time
	- Nodes and edges can be added and removed over time

## Characterizing Graphs

> [!danger]
> Don't memorize all of the following stuff! Memorize one or two maybe, but not all

### Graph Level Features

- Diameter: Longest shortest path
- Persistence: The smallest number of links whose removal increases the diameter or disconnects the graph
- Average in degree/out degree
- Nodes/edges added or deleted per time T
- Distribution of degree over the network

### Node Level Features

- In degree/out degree
- Degree centrality: Literally just the degree
	- Normalized degree centrality: That but normalized
- Closeness centrality: Importance measured by how close a vertex is to other vertices (takes into account average distance to all other nodes)
- Betweenness centrality: Number of shortest paths that pass through that vertex
- Eigenvector centrality: A vertex's importance is determined by importance of its neighborsco

## Link Prediction / Anomaly Detection

We would like to predict when a link forms in a graph:
- Recommend friends on Facebook
- Figure out who will be new terrorists
- Predict where money/resources will flow

On the flip side, if we can predict when a link will form, we can measure how unexpected a link is:
- Fraudulent transactions in financial networks
- Suspicious network traffic on a computer network

How can we turn this into a typical ML problem?

One way is to turn it into a supervised learning style problem.
- For each pair of nodes, generate some features, and use nodes with links as positive examples and nodes without as negative
- Examples of features:
	- How many neighbors the nodes have in common
	- Jaccard Coefficient
	- Number of length 3 paths between them

### Supervised Learning

We want to predict whether or not a link will form between two nodes at time $t+1$

> [!tip] Tip for final project
> `class_weight` is an important hyperparameter for decision trees in sklearn because of [class imbalance](Classification/Class%20Imbalance.md)

Challenges with evaluating link prediction models:
- Real world networks are very large and sparse
- Links have direction (different from typical classification problems)
- Networks change over time

## Community Detection

### Network topology

- An edge is a **bridge** if removing it makes the graph disconnected
- Bridges are weak ties connecting two different communities
- Bridges are rare in real life, but can relax the definition: an edge is a **"shortcut" bridge** if removing it causes the distance between two terminal vertices to increase
	- The larger the distance, the weaker the tie is

### Girvan-Newman Method

Results in a **hierarchical partitioning** of the graph

- Remove the edges of highest betweenness first
- Repeat the same step with the remaining graph
- Continue this until the graph breaks down into individual nodes

As the graph breaks down into pieces, the tightly knit community structure is exposed
