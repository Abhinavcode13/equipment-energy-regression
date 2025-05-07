## Data Handling and Model Optimization Summary

### How were missing values handled?
Missing values in the target (energy consumption) were filled using the median value. For numerical data, missing values were also replaced with the median, while missing values in categorical columns were filled using the most common value.

### What kind of scaling was applied?
A `MinMaxScaler` was used to scale all numerical features between `0` and `1`. This was applied to both original and newly created numerical features.

### What time-based features were created?
The timestamp column was converted to a datetime format. New features like hour, day of the week, and month were added. To better capture patterns, `cyclical transformations` were applied (e.g., turning hour and day into `sine` and `cosine` values).

### How were the random variables handled?
The code includes a part (commented out) suggesting these variables might be dropped based on low correlation. While no clear decision was made in the code, further analysis compared models with and without these variables to see how they affected performance.

### Which model was used and how was it tuned?
A `RandomForestRegressor` was trained. `GridSearchCV` was used to tune parameters like number of trees, depth of the trees, and splitting rules.

### Which metrics were used to evaluate the model?
The model’s performance was measured using `MSE`, `RMSE`, `MAE`, and `R-squared`.

### What happened when random variables were removed?
A separate model was trained without the random variables, and its results were compared to the original model to understand how much those variables influenced accuracy.


