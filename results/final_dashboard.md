# Multi-Model Stock Prediction Final Dashboard

Date Generated: 2025-10-07 13:50:29

---
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
![AAPL Best Model Forecast](eda_plots/AAPL_arima_wfv_forecast.png)

### GOOG: **ARIMA** (MAPE: 1.69%)
The **ARIMA** model provided the most accurate forecast for GOOG.
Visualizing ARIMA Forecast:
![GOOG Best Model Forecast](eda_plots/GOOG_arima_wfv_forecast.png)

### MSFT: **ARIMA** (MAPE: 1.24%)
The **ARIMA** model provided the most accurate forecast for MSFT.
Visualizing ARIMA Forecast:
![MSFT Best Model Forecast](eda_plots/MSFT_arima_wfv_forecast.png)

### TSLA: **ARIMA** (MAPE: 3.62%)
The **ARIMA** model provided the most accurate forecast for TSLA.
Visualizing ARIMA Forecast:
![TSLA Best Model Forecast](eda_plots/TSLA_arima_wfv_forecast.png)

---
## Forecast and Feature Importance Artifacts
All visual artifacts are saved in the `eda_plots` directory.

**Key Forecast Paths:**
* **AAPL LR WFV Forecast:** `eda_plots/AAPL_lr_wfv_forecast.png`
* **AAPL RF Feature Importance:** `eda_plots/AAPL_rf_feature_importance.png`
* **AAPL LSTM Forecast:** `eda_plots/AAPL_lstm_forecast.png`
* **GOOG LR WFV Forecast:** `eda_plots/GOOG_lr_wfv_forecast.png`
* **GOOG RF Feature Importance:** `eda_plots/GOOG_rf_feature_importance.png`
* **GOOG LSTM Forecast:** `eda_plots/GOOG_lstm_forecast.png`
* **MSFT LR WFV Forecast:** `eda_plots/MSFT_lr_wfv_forecast.png`
* **MSFT RF Feature Importance:** `eda_plots/MSFT_rf_feature_importance.png`
* **MSFT LSTM Forecast:** `eda_plots/MSFT_lstm_forecast.png`
* **TSLA LR WFV Forecast:** `eda_plots/TSLA_lr_wfv_forecast.png`
* **TSLA RF Feature Importance:** `eda_plots/TSLA_rf_feature_importance.png`
* **TSLA LSTM Forecast:** `eda_plots/TSLA_lstm_forecast.png`