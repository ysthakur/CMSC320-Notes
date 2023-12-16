#supervised-learning 

Recommendation engines use supervised learning

To measure whether or not a recommendation was successful, websites generally use thumbs up/down

They can also use the following:
- Whether you commented
- Click through rate for ads (how often it was clicked)
- How long you watched a video (less commonly used than thumbs up/down)
- Whether they rewatched a movie
- Whether they shared the video with friends

Need to deal with ratings being inflated/deflated (some people rate everything 5 stars or 1 star)

Example for recommending movies:
- Use runtime, genre, budget, etc. as features
- When a new movie comes, predict whether or not it will get a thumbs up

## Content Based Systems

- Featurize each item
- Build a model of what sorts of items the user likes (based off user's profile)
- Pick items that match their preferences that they haven't bought yet
- Show them those items

Weight more recent items more heavily (because tastes change over time)

Pros:
- No need for other users
- Recommend things to users with unique tastes
- Able to recommend new and unpopular items
- Able to provide explanations

Cons:
- Finding the appropriate features is hard
- User profile is hard to build
- Never recommends things outside the user's content profile
- Leaves information on the table
- Cold start problem: Don't have any information on new users
- **Needs retraining**

## Collaborative Filtering

- People who are similar enjoy similar things
- You can see how similar users are by turning them into vectors
- Can use something like KNN:
	- Given a user, find their K nearest neighbors
	- Predict the user's rating for some movie based on the weighted average of those user's ratings

Pros:
- Works for any item
- Uses more info
- Recommends items from outside users' comfort zones

Cons:
- Cold start problem
- Popularity bias - If a good movie has just shown up but no one has seen it, it won't be recommended (unlike content based filtering, which can featurize movies even if no one's watched them)

### Item-Based Collaborative Filtering

- 

## Evaluation

Problem with evaluating recommendation engines: 
- If someone didn't watch a movie (whether or not you recommended it), you have no way to tell if you were supposed to recommend that movie or not
- So you can evaluate true positives, but you can't tell if something is a false positive or a true negative

Evaluation methods:
- **Mean absolute error** (MAE)
	- MAE is the average of the differences between the ratings predicted by the recommender and the actual ratings given by the user
	- Basically treating it like regression: no training and test set, just train on the data you have, then look at the MAE
- Precision at top ten
	- For content based filtering, look at the 10 highest ranked things and compute the precision of that list (how many of those did we get right?)
	- However, the things the user didn't buy might just have been things they haven't heard of
- Per user leave-one-out-cross-validation
	- For each user, leave out one thing they've rated, then predict the rating
	- Can be used for collaborative filtering

Evaluation harder for collaborative filtering than content based filtering
- For content based filtering, you can take away 10% of the data and test the model on that
- But for collaborative filtering, if you take away 10% of the movies, the user is changed in a fundamental way. Cannot maintain robustness
