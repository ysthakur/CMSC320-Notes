Some ML models hate categorical data, which is where one hot encoding comes in

Make a separate column for each category, and put a 1 or 0 in each category’s column depending on whether that row is in that category

Pros:

- You get to use your categorical variables

Cons:

- If there are 50 categories, your dataset explodes

```python
pd.get_dummies(series)
```