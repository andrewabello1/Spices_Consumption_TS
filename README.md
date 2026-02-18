# Time Series Forecasting – Total Consumption Analysis

## Project Overview

This project analyzes and forecasts total yearly consumption using time series modeling techniques.  
The dataset was aggregated by year, combining all countries and items into a single annual consumption series.

The main objective was to compare multiple forecasting models and determine the most appropriate approach for predicting future consumption.

---

## Data Characteristics

- Frequency: **Yearly**
- Strong upward linear trend
- No visible seasonality
- Small sample size (~30 observations)

Since the data is annual, no seasonal component was expected or detected.

---

## Models Implemented

### Baseline Models
- Naive Forecast
- Historical Average
- Window (Moving) Average

These models were used as simple performance benchmarks.

### Holt’s Double Exponential Smoothing
- Trend-only model
- Captures level and linear trend
- No seasonal component

### ARIMA
- Log transformation applied
- Stationarity tested using Augmented Dickey-Fuller (ADF)
- Differencing applied when necessary
- Model selected using `auto_arima`

---

## Model Evaluation

Models were evaluated using:

- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**

A proper train-test split was performed, using the last 3 years as the test set.

---

## Best Model

Holt’s Double Exponential Smoothing achieved the lowest MAE and RMSE, outperforming both baseline models and ARIMA.

This indicates that the series is primarily driven by a stable linear trend rather than a complex stochastic process.

---

## Final Forecast

Using the best-performing Holt model refitted on the full dataset:

**Forecast for 2024: 68,922,690**

The forecast suggests a continuation of the historical upward trend.

---

## Key Takeaways

- Simpler models can outperform more complex models in small datasets.
- Log transformation does not always improve ARIMA performance.
- Annual trend-driven data is well-suited for Holt’s method.
- Proper model comparison using train-test splits is essential.

---

## Tools & Libraries

- Python  
- pandas  
- numpy  
- matplotlib  
- statsmodels  
- pmdarima  
- scikit-learn  
