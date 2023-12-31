
A time series is a dataset where the values are arranged in a sequence (doesn't actually have to be time)

We are concerned with predicting the next value in the sequence

## Filling in Missing Data

Missing data can be filled in with:
- Forward/backward fill, where you just fill in missing values by copying over the  previous or next values
	- If your time series has trend or seasonality, then this will screw that up over long time periods
- Mean/median/mode imputation - bad, can underestimate the variance
- Moving average
	- Takes into account temporal structure of data
	- But window size important: if too large, then smooths too much; if too small, then won't capture trend
	- ==todo when would you want to use this==
- Linear interpolation - Draw a line between the earliest and latest non-missing values
	- Works with linear trends, but not other trends
	- Doesn't work well for seasonal data
- Spline interpolation: Uses splines (piecewise polynomials)
	- More computationally expensive than previous approaches
	- Better than polynomial interpolation because can fit data well while still using low-degree polynomials
	- Smoother fit than linear interpolation because can curve
	- But needs data to be smooth
- KNN imputation
	- Computationally expensive, especially if have lots of features
- STL imputation - break apart into seasonality, trend, and residuals (noise), impute the residuals, then reassemble
	- Can capture complex seasonal patterns that other methods miss
	- Can handle any type of seasonality, not just monthly or quarterly

Aside from forward/backward fill and moving average, the rest were from [this article](https://medium.com/@aaabulkhair/data-imputation-demystified-time-series-data-69bc9c798cb7):

## Validation

> [!caution]
> Can't do normal cross-validation with time series

- Cut the time series off at a given point
- Predict the next period using mean squared error

## Time Series Components

- Noise: random jitters from things we can't see
	- Noise can be generated by any distribution, but is usually gaussian in nature
- Seasonality: Cyclic behavior
- Trend: Whether it's going up or down
	- A time series is **stationary** if it has a constant mean and variance (in which case it has no trend and no seasonality)

To find if time series is stationary, use Dickey-Fuller [hypothesis test](../Stats/Hypothesis%20and%20Inference.md)
- Dickey-Fuller checks if the time series has any **unit roots**
- **Unit roots** are a feature of time series that indicate if there is something affecting the data making it go away from the mean (seasonality or trend)

### Separating the components

These 3 components can be combined in either an additive or multiplicative way:
- Additive: Model the target variable as the **sum** of the three components
	- i.e., $y_i = t_i + s_i + n_i$, where $t_i$, $s_i$, and $n_i$ are the trend, seasonality, and noise at each time step $i$
- Multiplicative: Model the target variable as the **product** of the three components
	- i.e., $y_i = t_i \cdot s_i \cdot n_i$

Steps for separating components according to https://timeseriesreasoning.com/contents/time-series-decomposition/ and https://machinelearningmastery.com/time-series-seasonality-with-python/:
- Use smoothing to get rid of seasonality and noise and get the trend component
	- Can use centered moving average for this
- Then, decide whether the composition is additive or multiplicative (see above for notes)
	- If additive, subtract trend from original time series
	- If multiplicative, divide original time series by trend
- Now what you have left is either $s_i + n_i$ or $s_i \cdot n_i$, depending on whether you assumed additive or multiplicative composition
- Guess the season length? Here, suppose it's a year
	- ==todo is there a way to do it without guessing?==
- Calculate the average $y$ for every January month, every February month, etc.
	- This assumes that the data across all of January is more or less the same (works for things like temperature)
	- Otherwise, you could get the average of every first day in a year, every second day in a year, etc.
- This gives you the pure seasonality component
- Again, remove the seasonality component from the combined $s_i + n_i$ or $s_i n_i$ data
- What you have left is the noise component

## Smoothing

- We want to remove the noise to find the "true" series
- This may be a better predictor than the actual data

### Modeling

==TODO: Take notes on this==

### Moving Average

Also known as a rolling average

==TODO: Take notes on this==

#### Moving Average with Exponential Smoothing

- Exponential smoothing applies exponentially decreasing weights to previous observations
	- Because don't want previous observations to contribute too much
- $\alpha$ is a **smoothing factor** that takes values between 0 and 1
	- It determines how fast the weight decreases for previous observations
	- The lower the $\alpha$, the smoother it is
- Used when data **has no seasonality and no trend**
	- Only applies level smoothing, no trend smoothing or seasonal smoothing

Recursive formula (don't need to memorize):
$y_0 = x_0$, where $x_0$ is the actual value at time $t = 0$
$y_t = a x_t + (1 - \alpha) y_{t-1}$

#### Double Exponential Smoothing

- $\beta$ is the trend smoothing factor and takes values between 0 and 1
- The lower the $\beta$, the smoother it is
- Used when data **has a trend but no seasonality**
	- Applies level smoothing and trend smoothing but no seasonal smoothing

Recursive formula (don't need to memorize):
$y_t = a x_t + (1 - \alpha)(y_{t-1} + b_{t-1})$
$b_t = \beta(y_t - y_{t-1}) + (1 - \beta)b_{t-1}$

#### Triple Exponential Smoothing

- Used when data **has seasonality and trend**
	- Applies level smoothing, trend smoothing, and seasonal smoothing
- Uses parameter called $\gamma$ (gamma)

## Modeling

### Auto-Regressive Model

The AR model depends on its own past values (lags) to estimate future values

### Moving Average Model

The moving-average MA model depends on past forecast errors to make predictions

### Auto-Regressive Model

The AR model only depends on past values (lags) to estimate future values

Can handle trend but not seasonality

Takes 3 hyperparameters:
- p (lag order): number of lag observations in the model
- d (degree of differencing): number of times the raw observations are differenced
- q (order of the moving average): size of the moving average window
