# Google Stock Price Forecasting using ARIMA & CNN-LSTM

This project presents a complete time-series forecasting pipeline for Google (GOOGL) stock prices, comparing classical statistical modeling with modern deep learning techniques. The objective is to understand historical stock behaviour, identify underlying trends, and evaluate the predictive performance of ARIMA and CNN-LSTM models. The analysis highlights the superiority of deep learning in capturing nonlinear financial patterns and producing accurate forecasts.

🚀 ***Project Overview***

The goal of this project is to analyze historical Google stock prices and develop predictive models that can forecast future closing prices. The pipeline covers:

* Data cleaning & preprocessing <br>
* Full exploratory time-series analysis <br>
* Trend–seasonality understanding <br>
* Classical ARIMA modeling<br>
* Deep learning using CNN-LSTM<br>
* Model evaluation & comparison<br>

📊 ***1. Exploratory Data Analysis (EDA)*** 

The link to dataset.

The dataset consists of daily historical stock market data, containing the following fields:
**Date** – Trading day timestamp
**Open** – Opening price of the stock
**High** – Highest price reached during the day
**Low** – Lowest price during the day
**Close** – Closing price of the stock
This structure provides a comprehensive view of price movement and market activity, which is essential for time-series forecasting and technical analysis.

* Converted the Date column to proper DateTime format and set it as the index for time-series operations.
* Verified dataset integrity by checking for missing or null values; none were found.
* Computed essential technical indicators, including 50-day and 200-day moving averages for trend identification.
* Calculated daily returns and analyzed their distribution to understand price variability.
* Performed volatility analysis to identify periods of high and low market risk.
* Generated monthly and daily average plots to explore seasonal and temporal behavior.
* Created a correlation heatmap to understand relationships among price features.
* Visualized price movement using a candlestick chart, giving a clear picture of daily market dynamics.

This provided a complete statistical and visual understanding of historical GOOGL price behaviour.

🧪 ***Classical ARIMA Modeling***<br>
* Data was split into training and testing sets, and Additive Seasonal Decomposition was applied to extract trend, seasonality, and residuals.
* The series was found to be non-stationary and required transformation for modeling.
* ADF test confirmed stationarity after first-order differencing (d = 1).
* ACF and PACF plots suggested ARIMA parameters p = 3 and q = 3, leading to the ARIMA(3,1,3) model.
* On the test set, ARIMA performed poorly (MAE = 60.19, RMSE = 67.01) due to its inability to capture nonlinear and volatile stock patterns.  
* Limitations of ARIMA for stock forecasting: <br>
Assumes linear relationships, cannot capture nonlinear patterns. Struggles with high volatility and abrupt fluctuations. Residuals indicate underfitting and poor generalization. Overall, ARIMA was unsuitable as a standalone model for forecasting Google stock prices.

🤖 ***CNN-LSTM Deep Learning Model***
* Implemented to capture nonlinear patterns and volatility in Google stock prices.
* Data was scaled with MinMaxScaler and converted into supervised sequences for training and testing.
* Model architecture: Conv1D → MaxPooling → LSTM → Dropout → Dense output.
* Performance: MAE = 4.27, RMSE = 5.41, Adjusted R² = 0.96, with strong generalization (Train R² = 0.995, Test R² = 0.962).
* Outperformed ARIMA by effectively capturing short-term fluctuations and long-term trends, producing highly accurate forecasts.
