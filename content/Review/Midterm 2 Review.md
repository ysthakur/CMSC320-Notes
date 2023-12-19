## [Feature Engineering](ML/Feature%20Engineering/Feature%20Engineering.md)

Topics:

- [One Hot Encoding](ML/Feature%20Engineering/One%20Hot%20Encoding.md)
- Normalization:
	- Put data into range `[0, 1]`
- Standardization:
	- Each data point becomes the number of standard deviations away from the mean it was (z-score)

Example questions:

1. Given some data, one hot encode it.
	- `pd.get_dummies`
2. **What sort of categorical columns might cause problems if you one-hot encoded them?**
3. Is it bad to one-hot encode ordinal data?
	- Yes, because then it's treated as categorical data
4. Does the base matter when you do a log transform?
	- No
5. Normalize a few datapoints.

## Supervised Learning

1. Make sure you deeply understand accuracy, precision and recall.
	- What happens if you flip precision and recall to be about the negative class, is that valid?
	- Can you come up with three examples of when you’d use precision and recall?
		- Precision:
			- If you're a (good) judge, you want to make sure everyone you convict is actually a bad person, even if you miss some bad people
			- Loans
		- Recall:
			- If you're a dictator executing people, you want to make sure all your enemies are executed, even if you execute a few innocent people
			- Fraud alerts
	- Do you ever care about both?
2. Log Loss was mentioned briefly, but it would be fun to create a question that plays with the model’s confidence in its predictions, the thing log loss cares about.
3. When might 80% accuracy not be meaningful? If your data is super heavy with one particular class, how might you better see what’s going on with the model?
	- Class imbalance would make accuracy less useful
	- Confusion matrix can help look at results. Also precision, recall
1. Make sure you understand the difference between train test split and the different forms of cross validation. HW5 is a good guide here, since you got to practice a few different examples. These concepts are all a little similar, so make sure there’s no mental clashing between them. Would we ever do 2 fold cross validation? Why or why not?
2. Over and underfitting are really important concepts. Try creating a dataset and designing and overfit tree and an underfit one. Understand the signs of over and underfitting, and how you might fix them.
3. What do fit() and predict() do?

### [KNN](ML/Classification/KNN.md)

1. What happens as k gets bigger or smaller? How does that relate to underfitting and overfitting?
2. Draw a dataset and try classifying a point with k=3.
3. When does spherical KNN do better than the normal algorithm?
	- When there's lots of data points, since searching all points is time-consuming
4. ==When will a decision tree outperform KNN? When will KNN outperform a decision tree?==

### [Decision Trees](ML/Classification/Decision%20Trees.md)

1. Try generating some data and drawing the decision tree it creates, doing the splits out at each level.
2. Can you come up with the formula for info gain from scratch? Try writing out the algorithm and generating it without looking.
3. Draw a strangely shaped decision tree. What would it say about your data?
4. What does half a bit mean when it comes to entropy?

## Unsupervised Learning

### K-Means [Clustering](ML/Feature%20Engineering/Clustering.md)

1. What happens as k goes up? What about down?
2. What is the loss function? You should at the very least be able to describe it via words; worst case you should be able to construct an equation for it.
3. Draw a bunch of points and some centroids, and mentally run through a few different iterations of your algorithm.
4. How do you pick the best K? What is that one graph in the slides, and why are we looking for the minima?
5. What is the point of doing k-means in the first place? When would you use agglomerative clustering instead of k-means?

### [PCA](ML/Feature%20Engineering/PCA.md)

1. When do we use PCA, and why?
2. ==When is PCA lossless and when is it lossy?==
	- When two or more columns are correlated, PCA could be lossless
	- Otherwise, it will be lossy
1. Draw some data with high covariance, and draw the first principle component.
2. Draw some data with low covariance.

## [Regression](ML/Regression.md)

1. What does $R^2$ mean? What's the equation?
2. Can $R^2$ ever be negative? What does it mean if it is?
	- If $r^2$ is negative, then you're doing worse than just predicting the mean for every data point, and something's gone horribly wrong
3. ==What does it mean if you have a situation where no single line can accurately classify your data?==
	- Maybe linear regression is the wrong choice, try other kinds of regression?
4. Try finding a dataset and running your own regression on it.

## [Neural Networks](ML/Neural%20Networks/Neural%20Networks.md)

1. **Generate a small neural network and show the output for a small input.**
2. Generate a network that computes xor of its inputs.
	- (can be done easily using ReLU)
3. Be able to define neuron, activation value, activation function, sigmoid (no need to even look at the equation on this one), and other terms of that generality.
	- Neuron: A computational unit; a node in the graph of the network
	- Activation value: Represents how activated a particular neuron is
	- Activation function: Calculates output of neuron
	- Sigmoid function:
		- An activation function with outputs in the range `[0, 1]`
		- Looks kinda like a very distorted S
4. Review how perceptrons work and how they classify things

## Stuff from [Midterm 1 Review](Review/Midterm%201%20Review.md 1 Review.md>)
