# Energy-Demand-Forecasting-XGBoost
A time series forecasting pipeline using XGBoost to predict hourly energy consumption.
This repository contains a Time Series Forecasting machine learning pipeline using XGBoost. The model is built to predict hourly energy demand using historical consumption data from the American Electric Power (AEP) dataset.

Project Overview

Time series forecasting is a critical component of energy grid management. This project demonstrates how to transform raw datetime data into actionable machine learning features and train a robust gradient boosted tree model to predict future energy loads.

Key Achievements & Workflow:

Time-Series Data Handling: Loaded the AEP_hourly.csv dataset, set the Datetime column as the DataFrame index, and ensured proper chronological sorting to prevent future data leakage.

Feature Engineering: Extracted temporal features directly from the index (e.g., hour, dayofweek, month, dayofyear). This allows tabular models like XGBoost to capture seasonality, daily trends, and cyclical patterns.

Train/Test Splitting: Instead of a random split, the data was split chronologically to simulate a real-world forecasting scenario (training on the past to predict the future).

Model Training & Evaluation: * Trained an XGBRegressor on the engineered features.

Evaluated the model using RMSE (Root Mean Squared Error) to heavily penalize large forecasting errors, establishing a strong predictive baseline.

Plotted the actual vs. predicted values to visually inspect the model's performance across different time horizons.

Repository Contents

XGboost (2).ipynb: The complete Jupyter Notebook containing the EDA, feature engineering, and model training.

AEP_hourly.csv: The hourly energy consumption dataset used for model training.

Future Improvements

To further minimize the RMSE and capture more complex patterns, future iterations of this pipeline may include:

Lag Features: Incorporating historical lag variables (e.g., energy consumption 24 hours ago, 1 week ago).

Rolling Window Statistics: Adding rolling means and standard deviations to capture short-term momentum.

Hyperparameter Optimization: Utilizing tools like Optuna or GridSearchCV to fine-tune XGBoost parameters (learning_rate, max_depth, n_estimators).
