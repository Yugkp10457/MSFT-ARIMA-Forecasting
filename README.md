# MSFT-ARIMA-Forecasting
Time Series Analysis and Forecasting of Microsoft (MSFT) Stock Prices using the ARIMA model

🎯 Project Overview & Goal

This project implements a classical ARIMA (Autoregressive Integrated Moving Average) model to forecast the closing price of Microsoft Corporation ($MSFT) stock. The primary goal was to establish a forecasting baseline and critically evaluate the limitations of linear time series models when applied to highly volatile, non-linear financial data.

Time Span: January 1, 2020, to September 30, 2025 (data updated as of last run).

Model Used: ARIMA(3,1,2)

📉 Results and Critical Evaluation

The high errors confirm the model's insufficiency for practical forecasting against recent market volatility.

Performance Metrics (365-Day Test Set)
Root Mean Squared Error (RMSE): The RMSE is $49.01. This represents the typical magnitude of the error, indicating several large prediction misses.

Mean Absolute Error (MAE): The MAE is $35.05. This means the forecast was, on average, off by over $35 per share.

🔍 Methodology Summary

Data Acquisition & Preparation: 

Used the yfinance library to retrieve daily stock prices, followed by cleaning and date-time indexing.

Stationarity: Verified non-stationarity using the ADF Test, necessitating first-order differencing ($d=1$) to stabilize the data.

Model Identification: Used ACF and PACF plots on the differenced returns to guide the selection of the initial parameters ($p=3, q=2$).

Training & Validation: The model was trained on the historical data and evaluated using RMSE/MAE on a 365-day test set.

🚀 Next Steps (Future Work)
The model's high error rate proves the need to transition to techniques that handle financial non-linearity and memory effects:

Deep Learning (LSTM): Implementing a Long Short-Term Memory (LSTM) network to capture non-linear dependencies and long-term memory effects.

SARIMA / Auto ARIMA: Exploring Seasonal ARIMA or using an automated search like Auto ARIMA to optimize the statistical model order.
