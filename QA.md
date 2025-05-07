## Data Handling and Model Optimization Summary

#### How were missing values handled?
Missing values in the target (energy consumption) were filled using the median value. For numerical data, missing values were also replaced with the median, while missing values in categorical columns were filled using the most common value.

#### What kind of scaling was applied?
A `MinMaxScaler` was used to scale all numerical features between `0` and `1`. This was applied to both original and newly created numerical features.

#### What time-based features were created?
The timestamp column was converted to a datetime format. New features like hour, day of the week, and month were added. To better capture patterns, `cyclical transformations` were applied (e.g., turning hour and day into `sine` and `cosine` values).

#### How were the random variables handled?
The code includes a part (commented out) suggesting these variables might be dropped based on low correlation. While no clear decision was made in the code, further analysis compared models with and without these variables to see how they affected performance.

#### Which model was used and how was it tuned?
A `RandomForestRegressor` was trained. `GridSearchCV` was used to tune parameters like number of trees, depth of the trees, and splitting rules.

#### Which metrics were used to evaluate the model?
The model’s performance was measured using `MSE`, `RMSE`, `MAE`, and `R-squared`.

#### What happened when random variables were removed?
A separate model was trained without the random variables, and its results were compared to the original model to understand how much those variables influenced accuracy.

---

## Key Data Analysis Findings

#### Handling Missing Data:
Missing values were filled in thoughtfully: median for numerical and target columns, mode for categorical ones.

#### Feature Engineering:
New features included combinations like temperature and humidity, rolling averages and standard deviations (1-hour window), and 1-hour lagged values. Time features were also encoded to capture daily and weekly cycles better.

#### Model Tuning:
The best model settings from tuning were: max depth of `10`, `50` trees, and default splitting rules. This led to better model accuracy.

#### Model Performance:
The final model performed very well, with a very high `R-squared (0.9955)`, `very low MAE (0.0008)`, and `RMSE (0.0052)`, suggesting predictions were extremely accurate.

#### Feature Importance:
The model identified the top 10 most important features, though the exact list wasn’t shared.

#### Effect of Random Variables:
Comparing models with and without the random variables helped evaluate whether they were useful. Without random variable there is not much effect on the evaluation part.
