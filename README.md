# Stock_Prediction_Capstone_Part2
<img width="1536" height="1024" alt="Project_chart" src="https://github.com/user-attachments/assets/e0079d78-92a1-431f-a197-95c824c5ba63" />

This Project focuses on improving stock price predictions. Building upon the initial Capstone project where a linear regression model predicted the next 7-day stock prices for top US stocks (Tesla (TSLA), Apple (AAPL), Google, and Microsoft (MSFT)) using 5 years of time-series data, this project explored and iteratively improved those predictions. We achieved this by utilizing more advanced models such as Random Forest, ARIMA, and LSTM.

The goal of this project was to establish a rigorous comparison between classical statistical models and modern deep learning techniques for predicting the **7-day Adjusted Closing Price of top US stocks (AAPL, GOOG, MSFT, TSLA).**

The project successfully moved beyond static splitting by implementing **Walk-Forward Validation (WFV)**, ensuring highly reliable backtested metrics. The final results demonstrate a significant finding: **the ARIMA (SARIMAX) model consistently achieved the lowest MAPE and RMSE across all four tickers, validating that robust statistical time-series methods, when paired with macro features, can significantly outperform complex deep learning models (LSTM)** on this specific short-term forecasting task.

## Overall Performance Leaderboard (Lowest MAPE is Best)
| Ticker   | Model   |   RMSE |   MAPE |
|:---------|:--------|-------:|-------:|
| MSFT     | ARIMA   |   8.36 |   1.24 |
| GOOG     | ARIMA   |   4.53 |   1.69 |
| AAPL     | ARIMA   |   5.94 |   1.71 |
| MSFT     | LR      |  13.19 |   2.37 |
| AAPL     | LR      |   9.08 |   2.88 |
| GOOG     | LR      |   7.27 |   2.94 |
| MSFT     | RF      |  19.25 |   3.33 |
| TSLA     | ARIMA   |  16.84 |   3.62 |
| AAPL     | RF      |  11.39 |   4.07 |
| GOOG     | RF      |   9.75 |   4.08 |
| TSLA     | LR      |  27.41 |   7.11 |
| TSLA     | RF      |  32.20 |   7.86 |
| AAPL     | LSTM    |  43.53 |  19.83 |
| MSFT     | LSTM    | 109.94 |  23.54 |
| TSLA     | LSTM    |  97.54 |  29.69 |
| GOOG     | LSTM    |  66.49 |  36.06 |


## Best Performing Model Per Stock

### AAPL: **ARIMA** (MAPE: 1.71%)
The **ARIMA** model provided the most accurate forecast for AAPL.
Visualizing ARIMA Forecast:
![AAPL Best Model Forecast](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/AAPL_arima%20(wfv)_forecast.png)

### GOOG: **ARIMA** (MAPE: 1.69%)
The **ARIMA** model provided the most accurate forecast for GOOG.
Visualizing ARIMA Forecast:
![GOOG Best Model Forecast](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/GOOG_arima%20(wfv)_forecast.png)

### MSFT: **ARIMA** (MAPE: 1.24%)
The **ARIMA** model provided the most accurate forecast for MSFT.
Visualizing ARIMA Forecast:
![MSFT Best Model Forecast](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/MSFT_arima%20(wfv)_forecast.png)

### TSLA: **ARIMA** (MAPE: 3.62%)
The **ARIMA** model provided the most accurate forecast for TSLA.
Visualizing ARIMA Forecast:
![TSLA Best Model Forecast](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/TSLA_arima%20(wfv)_forecast.png)
## Baseline of the Capstone Project part 1

In the Capstone Project part 1, i had established a **Linear Regression (LR) baseline model** for forecasting the daily Adjusted Closing Price of four **major US stocks (AAPL, GOOG, MSFT, TSLA).** The model uses five years of historical data and incorporates **macroeconomic indicators (VIX, SPY) and technical features (Moving Average, Volatility)** to predict the price for a 7-day forecast period.

The primary purpose of this baseline was to **provide a measurable benchmark**. We had a goal to improve upon these initial results using more **advanced models (Random Forest, ARIMA, LSTM)** in Part2 of this Capstone project.

<img width="1108" height="415" alt="Screenshot 2025-09-29 at 3 52 27 PM" src="https://github.com/user-attachments/assets/47fb2c9a-f771-4da6-903e-6ef71f1042e7" />
