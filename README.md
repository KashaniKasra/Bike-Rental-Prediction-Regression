# Bike Rental Demand Prediction (Regression)

This project builds a supervised machine learning regression model to predict the number of daily bike rentals based on weather, seasonal, and calendar-related features.

## Goal
Predict the `total_users` for each day using the provided features and generate predictions for the unlabeled test set.

---

## Dataset

### Input Files
- `train_data.csv`: Contains features and actual number of users for training.
- `test_data.csv`: Same features without labels; used for generating predictions.

### Features
- **Date/Calendar Features**: `date`, `season_id`, `month`, `weekday`, `is_holiday`, `is_workingday`, `year`
- **Weather Features**: `weather_condition`, `temperature`, `feels_like_temp`, `humidity`, `wind_speed`
- **Target Variable**: `total_users`

---

## Pipeline Summary

### 1. Data Exploration
- Visualized correlations between temperature, humidity, day type, and rental count.
- Identified seasonal and weather-based rental trends.

### 2. Preprocessing
- One-hot encoded categorical variables.
- Standardized continuous features.
- Created new time-based features (e.g., lag between date and year, weekday categories).

### 3. Feature Selection
- Performed correlation analysis and statistical significance testing (p-values) to retain impactful variables.

### 4. Model Training
- Compared models: Linear Regression, Random Forest, Gradient Boosting, and XGBoost.
- Used cross-validation and grid search for tuning.
- Final model: Gradient Boosting Regressor with optimal parameters.

### 5. Prediction & Submission
- Predicted `total_users` for test data.
- Output format: CSV file with `id` and `label` (prediction).

---

## Evaluation Metrics
Although predictions are submitted externally, the notebook includes internal evaluations using:
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R-Squared Score (R²)
- Mean Absolute Percentage Error (MAPE)
- Mean Absolute Error (MAE)

---

## Tools & Libraries
- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Scikit-learn
- XGBoost
- Jupyter Notebook

---

## Submission Format
- `submission.csv` with:
  - `id`: Index of the sample
  - `label`: Predicted total users for that day