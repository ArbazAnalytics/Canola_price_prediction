Canola Price Prediction Project
Overview
This project aims to predict the price of Canola using historical data, weather conditions, and inflation rates. The data was collected from various sources, including government websites, and preprocessed to create a unified dataset. Multiple machine learning models were trained and evaluated to predict Canola prices accurately.

Project Steps
Data Collection:

Collected data from government websites and other sources (see References).

Data included historical prices, weather conditions (temperature, precipitation), and inflation rates.

Data Preprocessing:

Formatted and merged data into a single table.

Pivoted and unpivoted data to align all fields.

Calculated the mean of monthly prices (since prices were provided 4 times a month).

Feature Engineering:

Standardized features using StandardScaler for better model performance.

Identified and removed irrelevant features (e.g., precipitation) to improve model accuracy.

Model Training and Evaluation:

Trained and compared multiple models:

Linear Regression

Random Forest

XGBoost

Evaluated models using metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² Score.

Hyperparameter Tuning:

Used GridSearchCV and RandomizedSearchCV to optimize hyperparameters for Random Forest and XGBoost.

Feature Importance:

Analyzed feature importance to identify key factors influencing Canola prices.

Final Predictions:

Saved predictions to a CSV file for further analysis.

Observations and Results
Linear Regression
Without Standard Scaler:

MAE: 25.17

MSE: 923.22

RMSE: 30.38

R²: -0.27

With Standard Scaler:

MAE: 24.14

MSE: 731.61

RMSE: 27.05

R²: 0.03

Random Forest
MAE: 14.15

MSE: 236.68

RMSE: 15.38

R²: 0.63

XGBoost
MAE: 9.30

MSE: 122.71

RMSE: 11.08

R²: 0.81

After removing the least relevant column (precipitation):

MAE: 9.18

MSE: 114.93

RMSE: 10.72

R²: 0.82

Key Factors
Unit: Metric tonnes

Timeframe: Data analyzed from 2015 to 2020

Inflation: Included as a feature to account for economic changes.

Weather Conditions:

Temperature (Regina, SK, 2m above ground)

Precipitation

Historical Prices: Used as the primary target variable.

Code Structure
The project code is organized as follows:

Data Loading and Preprocessing:

Load and clean data.

Merge and pivot/unpivot data.

Calculate monthly mean prices.

Feature Engineering:

Standardize features using StandardScaler.

Remove irrelevant features.

Model Training and Evaluation:

Train Linear Regression, Random Forest, and XGBoost models.

Evaluate models using MAE, MSE, RMSE, and R².

Hyperparameter Tuning:

Optimize Random Forest and XGBoost using GridSearchCV and RandomizedSearchCV.

Feature Importance:

Analyze and visualize feature importance.

Final Predictions:

Save predictions to a CSV file.

References
Data Sources
Production Data:

Statistics Canada - Monthly Canola Production

Weather Data:

NASA POWER Data Access Viewer

How to Run the Code
Clone the repository:

bash
Copy
git clone https://github.com/your-username/canola-price-prediction.git
Install the required libraries:

bash
Copy
pip install pandas numpy scikit-learn xgboost matplotlib seaborn
Run the Jupyter Notebook or Python script:

bash
Copy
jupyter notebook canola_price_prediction.ipynb
Check the output CSV file for predictions:

predicted_results_without_production.csv
