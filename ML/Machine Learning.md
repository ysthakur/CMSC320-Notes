
## Vocabulary

- Instance based model: Requires all training data to be stored to work
- Hyperparameter: Argument to the model that determines how the model behaves
- Model: a mathematical object that
    - takes your training data,
    - learns a function mapping data to labels,
    - and then is able to take unlabeled data and assign it labels

## Classification Problems

A type of supervised machine learning

Goal: Assign categories or labels to data points based on patterns in the data

- There’s a target variable you want to predict
- You have historical data where the target label is **known**
- You have new data where the target variable is **unknown**

## Data Splits

Data is split into three categories:

- Training data
- Testing data
- Validation data

## Types of Learning

- Supervised learning: Learns from labeled data where each example in training set has known target or output
    - Classification: Target is discrete
    - Regression: Target is continuous
- Unsupervised learning: Learns from unlabeled data and tries to identify patterns or structures within data
    - e.g. clustering similar points or reducing dimensionality
- Reinforcement learning: Learns to make sequence of decisions to maximize reward
    - Uses rewards and punishments
    - Used in robotics, games, autonomous systems

## Subtopics

- [Feature Engineering](Feature%20Engineering/Feature%20Engineering.md)
- [Evaluation](Model%20Evaluation/Evaluation.md)
- [Classification](Classification/Classification.md)
- [Regression](Regression.md)
- [Neural Networks](Neural%20Networks/Neural%20Networks.md)
- [Debugging models](Debugging%20models.md)