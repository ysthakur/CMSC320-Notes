## Math Stuff

- Bayes rule
- Probability calculations
- Conditional probability
- Expected value

## Stat stuff
### [Distributions](Stats/Probability%20Distributions%20and%20Summary%20Stats.md)

Types of distributions:
- Normal
- Poisson
- Uniform
- Binomial
- Bimodal ones

Questions:
1. Why is the Poisson distribution different from a normal distribution?
Because it's for
2. Are Poissons always symmetrical? Explain.
No, it's skewed right a bit. ==todo explain==
3. Why aren't Poissons always symmetrical?
==todo answer==
4. What does standard deviation mean in a normal distribution?
A larger standard deviation means the distribution has a wider range, while a smaller standard deviation means it has a smaller range.
5. Draw a normal distribution with a small and large standard deviation.
6. If a distribution has a longer left tail, can it be normal? What if the mean is shifted right?
If the left tail is longer than the right tail, then it's not normal. The mean can be anywhere you want, though, and the standard deviation can also be whatever you want.
7. How and why might you use the central limit theorem?
==todo answer==

### [Hypothesis testing](Stats/Hypothesis%20and%20Inference.md)

Types of hypothesis tests:
- Z-test (not mentioned in review guide but good to know anyway)
	- Use if population variance known OR if sample size > 30
	- Continuous data
	- Parametric
- T-test
	- Use if population variance unknown AND sample size < 30
	- Continuous data
	- Parametric
- ANOVA
	- Multiple groups
	- Continuous data
	- Parametric
- Chi-squared
	- Categorical data
- Mann-Whitney
	- Ordinal or continuous data
	- Non-parametric
- Dicky-Fuller
	- Used for checking if time series are stationary
	- A time series is stationary if it has no trend (if it has a constant mean and variance)
- Correlation coefficient
	- ==todo what does this have to do with hypothesis testing==

==todo answer these==
Questions:
1. Does p-value have anything to do with effect size? If so, how might they relate?
2. Dicky-Fuller tests for a unit root in a time series? What does that mean?
3. When might you choose a significance level higher than .05? What about one that's lower?

## Data Cleaning

Questions:
1. What is mode imputation, and when would you use it over mean imputation?
Replace missing values with the mode. Would use it over mean imputation if data is categorical or ordinal.
2. When can't you use mean imputation?
Can't use mean imputation for categorical or ordinal data
3. How might you fill in missing values in time series? Is that appropriate over super long gaps?
==todo take notes on time series imputation==
4. On a time series, when might using pure foreword fill give you a bad
answer for filling in gaps? What about a situation where you could do
better than imputing by drawing a line between the earliest non-missing
point and the last non-missing point?
==todo answer==
5. What is a z-score?
How many standard deviations away from the mean you are (standardization). Z-score can be negative

## [Feature Engineering](ML/Feature%20Engineering/Feature%20Engineering.md)

1. Given some data, one hot encode it.
2. What sort of categorical columns might cause problems if you one-hot
encoded them?
==todo answer==
3. Is it bad to one-hot encode ordinal data?
Yes, because it loses order and increases dimensionality
4. Does the base matter when you do a log transform?
Nope, just needs to be consistent.
5. Normalize a few datapoints.

## Supervised Learning

1. Make sure you deeply understand accuracy, precision and recall. What happens if you flip precision and recall to be about the negative class, is that valid? Can you come up with three examples of when you'd use precision and recall? Do you ever care about both?
==todo review precision and recall formulas==
2. Log Loss was mentioned briefly, but it would be fun to create a question that plays with the model’s confidence in its predictions, the thing log loss cares about.
3. When might 80% accuracy not be meaningful? If your data is super heavy with one particular class, how might you better see what’s going on with the model?
Make a confusion matrix to see your false negative and false positive rate
4. Make sure you understand the difference between train test split and the different forms of cross validation. HW5 is a good guide here, since you got to practice a few different examples. These concepts are all a little similar, so make sure there’s no mental clashing between them. Would we ever do 2 fold cross validation? Why or why not?
2-fold cross validation would probably not be a good idea, because you'd only get 50% of the data to train on every time. This will probably result in your models underfitting.
5. Over and underfitting are really important concepts. Try creating a dataset and designing and overfit tree and an underfit one. Understand the signs of over and underfitting, and how you might fix them.
6. What do fit() and predict() do?
`fit()` trains the model, while `predict()` uses the model to predict the target variable for some data

### [KNN](ML/Classification/KNN.md)

1. What happens as k gets bigger or smaller? How does that relate to underfitting and overfitting?
As k gets bigger, you start considering too many of your neighbors, so it's too general and will be underfitted. As k gets to 1, you only consider the closest few neighbors, so it's too specific and will overfit.
2. Draw a dataset and try classifying a point with k=3.
3. When does spherical KNN do better than the normal algorithm?
Normal KNN has to search all the points, which is slow. Spherical KNN only searches points within a sphere, which is faster.
5. When will a decision tree outperform KNN? When will KNN outperform a decision tree?
==todo answer==

### [Decision Trees](ML/Classification/Decision%20Trees.md)

Things to know about them:
- Strengths
- Weaknesses
- Training algorithm
- Hyperparameters
	- Max depth
- How they classify data
- Entropy

==TODO go through these questions==
Questions:
1. Try generating some data and drawing the decision tree it creates, doing the splits out at each level.
2. Can you come up with the formula for info gain from scratch? Try writing out the algorithm and generating it without looking. (Because me highlighting this means you have the opportunity to memorize the equation, if I ask a question like this I’ll probably describe a similar process and ask you to generate the equation for that. This is why I don’t like practice problems; it gives you the opportunity to memorize something, which means if I want to disambiguate between memorization and understanding, the test has to get harder.)
3. Draw a strangely shaped decision tree. What would it say about your data?
4. What does half a bit mean when it comes to entropy?

## Unsupervised Learning

### [K-Means](ML/Feature%20Engineering/Clustering.md)

==TODO go through these questions==
1. What happens as k goes up? What about down?
As k goes up, you start overfitting because each node will get its own cluster, which won't tell you anything. As it goes down, all of the nodes will get put into a single cluster, so you're underfitting and that's useless too.
2. What is the loss function? You should at the very least be able to describe it via words; worst case you should be able to construct an equation for it.
3. Draw a bunch of points and some centroids, and mentally run through a few different iterations of your algorithm.
4. How do you pick the best K? What is that one graph in the slides, and why are we looking for the minima?
5. What is the point of doing k-means in the first place? When would you use agglomerative clustering instead of k-means?

### [PCA](ML/Feature%20Engineering/PCA.md)

1. When do we use PCA, and why?
  - Reducing dimensionality to make training models easier
  - Visualization (turning into 2D or 3D)
  - Reducing noise
  - Feature selection: PCA ranks principal components, so that tells you which features explain the most variance
  - Potentially reveals hidden patterns by transforming original features into orthogonal components ==todo what does this mean==
2. When is PCA lossless and when is it lossy?
If you're trying to reduce $n$ dimensions to $m$ dimensions, then it'll be lossless if you have $n - m$ dimensions that are linear combinations of the other $m$ dimensions, and lossy otherwise
3. Draw some data with high covariance, and draw the first principle component.
==todo try this out==
4. Draw some data with low covariance.
==todo try this out==

## [Neural Networks](ML/Neural%20Networks/Neural%20Networks.md)

Things to know:
- Understand convolutional networks at a high level

==todo go through these questions==
Questions:
1. Generate a small neural network and show the output for a small input.
2. Generate a network that computes xor of its inputs.
3. Be able to define neuron, activation value, activation function, sigmoid (no need to even look at the equation on this one), and other terms of that generality.
4. Review how perceptrons work and how they classify things
5. What would happen if each neuron in the convolutional layer mapped to exactly one layer in the input? Would this work? How would that effect the network?
6. What is a convolutional layer, and how does it contribute to classification?

## [NLP](ML/NLP/NLP.md)

Topics:
- Sentiment analysis
- Topic modeling

==todo go through these questions==
Questions:
1. What information do you lose when you convert a vector to bag of words
something?
You lose information about the order of the words
2. For a tweet, what meta-data about the tweet might make useful features
for sentiment analysis?
Who posted it? ==todo think about this more==
3. How might you detect if two texts were generated by different authors?
4. How and why does tf-idf work?
5. What is cosine similarity, and how is it different from other distance measures? When might you use it vs other distance measures?

## [Graphs](ML/Graphs.md)

Topics:
- Girvan-Newman

Questions:
1. Can a node with low degree be critical to a graph’s connectedness?
Yes.
2. How might you describe a graph’s overall connectedness?
One way is persistence (the smallest number of edges you need to remove to increase the diameter or disconnect the graph)
3. What does it mean if you can remove 10% of a graph's nodes at random without lengthening the longest shortest path?
It's very well connected?
4. Given a good link prediction model, how could you use it for anomaly prediction?
If a link forms when we predicted that it *wouldn't* form, something's up.
5. The Girvan-Newman algorithm returns a hierarchical partitioning of a graph. What does that mean? What’s at the highest level, and what is at the lowest.
At the highest level is the entire graph, and the leaves are individual nodes.
6. How might you use what we've learned to write a link prediction algorithm from start to finish?
==todo answer this==
7. What challenges might there be in evaluating a link prediction model?
==todo answer this==

## [Time Series](Data%20Science/Time%20Series.md)

Things to know:
- Trend
- Seasonality
- Noise
- How to break down into trend, seasonality, and noise
- Imputation/filling in missing data
- Know names of algorithms for predicting stuff at next time step, but not the details

==todo go through these questions==
Questions:
1. Can a time series have multiple kinds of seasonality? What’s an example.
2. Why wouldn’t linear regression be a good choice for predicting a company’s earnings each month for the next year?
3. What is ARIMA?
Auto-Regressive Integrated Moving Average. ==todo what is it actually==
5. Why don't we use mode imputation for missing time series data?
6. What does it mean mathematically for a time series to be stationary?
7. When and why might you use a rolling average?
8. Can a rolling average over or underfit the curve? Come up with a real life set of parameters where that would be the case.

## [Recommendation Engines](ML/Recommendation%20Engines.md)

Things to know:
- Challenge: popularity bias
	- If you use collaborative filtering, it's possible that some movies are watched by practically everyone, while most are only watched by a handful
	- So those popular movies will keep being recommended while the unpopular ones will rarely/never be recommended
	- Like the cold start problem, using content-based filtering can help
- Content-based systems:
	- Pros:
		- ==todo==
		- Can recommend new content that no one's watched
	- Cons:
		- ==todo==
- Collaborative filtering:
	- Pros:
		- ==todo==
	- Cons:
		- ==todo==

==todo go through these questions==
Questions:
1. What is the cold start problem, and how can we fix it?
It's when you have a new user or a new item that you don't have any data on.
If it's a new user that you don't have data on, you can ask them to provide some preferences when signing up for your service, or you can just begin by recommending popular/random items to them.
If it's a new item that no one's seen, you can use content-based systems, or you can randomly recommend new items to people.
2. How can we tell if our recommendation algorithm is working well? What unique challenges does evaluating a recommendation algorithm present?