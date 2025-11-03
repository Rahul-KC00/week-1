# week-1
A machine learning model that predicts hourly household electricity demand using past usage patterns and weather conditions..
# Household Energy Consumption Forecasting

This project aims to forecast hourly household electricity consumption by analyzing historical energy usage along with hourly temperature data for Bangalore. The model is designed to identify how daily routines and external weather conditions influence power demand, providing insights that can support smart energy management and planning.

---

## Datasets Used

### 1. Household Power Consumption Dataset (UCI Repository)
This dataset contains minute-level measurements of household electricity usage recorded from 2006 to 2010.  
For this project, the data is resampled to hourly intervals to improve stability and forecasting performance.

Dataset Link:
https://archive.ics.uci.edu/ml/machine-learning-databases/00235/household_power_consumption.zip

### 2. Bangalore Hourly Temperature Data (Open-Meteo API)
Hourly temperature data is obtained to incorporate weather effects into the model. Temperature influences energy usage patterns, especially during heating and cooling conditions.

---

## Methodology

1. **Data Preprocessing**
   - Converted time columns into a unified datetime index.
   - Resampled raw data to hourly average consumption.
   - Handled missing values using forward and backward filling techniques.

2. **Feature Engineering**
   - Time-based features: hour of day, day of week, month, weekend indicator.
   - Lag features: previous 1, 2, 3, 6, 12, 24, 48, and 72-hour consumption values.
   - Rolling window features: 24-hour rolling mean and standard deviation.
   - Weather feature: hourly temperature (°C).

3. **Modeling**
   - A tuned XGBoost regression model is used for forecasting.
   - The dataset is split chronologically to prevent data leakage.

4. **Evaluation Metrics**
   - Mean Absolute Error (MAE)
   - Root Mean Squared Error (RMSE)
   - Mean Absolute Percentage Error (MAPE)

---

## Results Summary

The tuned XGBoost model effectively captures both temporal patterns and temperature influence on consumption.  
The model shows stable performance across multiple evaluation metrics, demonstrating its suitability for short-term electricity demand forecasting.

Applications include:
- Smart home energy automation
- Household load planning
- Demand-side energy management

---

## Future Improvements

- Incorporate additional weather parameters such as humidity and wind speed.
- Experiment with deep learning approaches such as LSTM networks for enhanced pattern recognition.
- Develop a real-time dashboard interface for live forecasting and monitoring.

