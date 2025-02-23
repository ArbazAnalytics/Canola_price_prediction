# Canola Price Prediction Project

## Overview
This project aims to predict the price of Canola using historical data, weather conditions, and inflation rates. The data was collected from various sources, including government websites, and preprocessed to create a unified dataset. Multiple machine learning models were trained and evaluated to predict Canola prices accurately.

---

## Project Steps
1. **Data Collection**:
   - Collected data from government websites and other sources (see References).
   - Data included historical prices, weather conditions (temperature, precipitation), and inflation rates.

2. **Data Preprocessing**:
   - Formatted and merged data into a single table.
   - Pivoted and unpivoted data to align all fields.
   - Calculated the mean of monthly prices (since prices were provided 4 times a month).

3. **Feature Engineering**:
   - Standardized features using `StandardScaler` for better model performance.
   - Identified and removed irrelevant features (e.g., precipitation) to improve model accuracy.

4. **Model Training and Evaluation**:
   - Trained and compared multiple models:
     - **Linear Regression**
     - **Random Forest**
     - **XGBoost**
   - Evaluated models using metrics like Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R² Score.

5. **Hyperparameter Tuning**:
   - Used `GridSearchCV` and `RandomizedSearchCV` to optimize hyperparameters for Random Forest and XGBoost.

6. **Feature Importance**:
   - Analyzed feature importance to identify key factors influencing Canola prices.

7. **Final Predictions**:
   - Saved predictions to a CSV file for further analysis.

---

## Observations and Results

### **Linear Regression**
- Without Standard Scaler:
  - MAE: 25.17
  - MSE: 923.22
  - RMSE: 30.38
  - R²: -0.27
- With Standard Scaler:
  - MAE: 24.14
  - MSE: 731.61
  - RMSE: 27.05
  - R²: 0.03

### **Random Forest**
- MAE: 14.15
- MSE: 236.68
- RMSE: 15.38
- R²: 0.63

### **XGBoost**
- MAE: 9.30
- MSE: 122.71
- RMSE: 11.08
- R²: 0.81
- After removing the least relevant column (precipitation):
  - MAE: 9.18
  - MSE: 114.93
  - RMSE: 10.72
  - R²: 0.82

---

## Key Factors
- **Unit**: Metric tonnes
- **Timeframe**: Data analyzed from 2015 to 2020
- **Inflation**: Included as a feature to account for economic changes.
- **Weather Conditions**:
  - Temperature (Regina, SK, 2m above ground)
  - Precipitation
- **Historical Prices**: Used as the primary target variable.

---

## Code Structure
The project code is organized as follows:
1. **Data Loading and Preprocessing**:
   - Load and clean data.
   - Merge and pivot/unpivot data.
   - Calculate monthly mean prices.
2. **Feature Engineering**:
   - Standardize features using `StandardScaler`.
   - Remove irrelevant features.
3. **Model Training and Evaluation**:
   - Train Linear Regression, Random Forest, and XGBoost models.
   - Evaluate models using MAE, MSE, RMSE, and R².
4. **Hyperparameter Tuning**:
   - Optimize Random Forest and XGBoost using `GridSearchCV` and `RandomizedSearchCV`.
5. **Feature Importance**:
   - Analyze and visualize feature importance.
6. **Final Predictions**:
   - Save predictions to a CSV file.

---

## References
### Data Sources
1. **Production Data**:
   - [Statistics Canada - Monthly Canola Production](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3210035101&pickMembers%5B0%5D=1.5&cubeTimeFrame.startMonth=01&cubeTimeFrame.startYear=2015&cubeTimeFrame.endMonth=01&cubeTimeFrame.endYear=2020&referencePeriods=20150101%2C20200101)
2. **Weather Data**:
   - [NASA POWER Data Access Viewer](https://power.larc.nasa.gov/data-access-viewer)

---

## How to Run the Code
1. Clone the repository:
   ```bash
   git clone https://github.com/ArbazAnalytics/Canola_price_prediction
   ```
2. Install the required libraries:
   ```bash
   pip install pandas numpy scikit-learn xgboost matplotlib seaborn
   ```
3. Run the Jupyter Notebook or Python script:
   ```bash
   jupyter notebook canola_price_prediction.ipynb
   ```
4. Check the output CSV file for predictions:
   - `predicted_results_without_production.csv`

---

## Future Work
- Incorporate additional features like global market trends, crop yields, and trade data.
- Experiment with more advanced models like LSTM for time-series forecasting.
- Deploy the model as a web application for real-time price predictions.
