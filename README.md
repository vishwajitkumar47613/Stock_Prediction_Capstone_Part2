# Stock_Prediction_Capstone_Part2
<img width="1536" height="1024" alt="Project_chart" src="https://github.com/user-attachments/assets/e0079d78-92a1-431f-a197-95c824c5ba63" />

## PROJECT SUMMARY

This Project focuses on improving stock price predictions. Building upon the initial Capstone project where a linear regression model predicted the next 7-day stock prices for top US stocks (Tesla (TSLA), Apple (AAPL), Google, and Microsoft (MSFT)) using 5 years of time-series data, this project explored and iteratively improved those predictions. We achieved this by utilizing more advanced models such as Random Forest, ARIMA, and LSTM.

The goal of this project was to establish a rigorous comparison between classical statistical models and modern deep learning techniques for predicting the **7-day Adjusted Closing Price of top US stocks (AAPL, GOOG, MSFT, TSLA).**

The project successfully moved beyond static splitting by implementing **Walk-Forward Validation (WFV)**, ensuring highly reliable backtested metrics. The final results demonstrate a significant finding: **the ARIMA (SARIMAX) model consistently achieved the lowest MAPE and RMSE across all four tickers, validating that robust statistical time-series methods, when paired with macro features, can significantly outperform complex deep learning models (LSTM)** on this specific short-term forecasting task.

![Jupyter Notebook Link](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/Top_US_Stocks_prediction_Part2.ipynb)

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

In the Capstone Project part 1, a **Linear Regression (LR) baseline model** was established for forecasting the daily Adjusted Closing Price of four **major US stocks (AAPL, GOOG, MSFT, TSLA).** The model uses five years of historical data and incorporates **macroeconomic indicators (VIX, SPY) and technical features (Moving Average, Volatility)** to predict the price for a 7-day forecast period.

The primary purpose of this baseline was to **provide a measurable benchmark**. We had a goal to improve upon these initial results using more **advanced models (Random Forest, ARIMA, LSTM)** in Part2 of this Capstone project.

<img width="1108" height="415" alt="Screenshot 2025-09-29 at 3 52 27 PM" src="https://github.com/user-attachments/assets/47fb2c9a-f771-4da6-903e-6ef71f1042e7" />

## PROJECT DETAILS

### KEY ENHANCEMENTS & METHODOLOGY

 This project incorporates several structural and algorithmic enhancements aimed at significantly improving model robustness and prediction accuracy compared to the LR baseline model from Capstone Project Part 1.


   - A. **Advanced Data Integration:**

       - **Multi-Lag Feature Engineering:** Technical indicators (MA, Volatility, Returns) are calculated across **multiple time windows (5, 20, and 60 days)** to give models both
         short-term and medium-term context.
         
       - **Macro Indicators:** Actual market data for **VIX (volatility)** and
         **SPY(market index)** is integrated as external features.



   - B. **Improved Validation Strategy (Critical Change):**

       - **Walk-Forward Validation (WFV):** The single 80/20 split is replaced. LR, Random Forest (RF), and ARIMA models are retrained every 7 days using all historical data up to             that point, providing the most realistic estimate of true forecast performance.



   - C. **Advanced Models:**

       - **Random Forest (RF):** Captures **non-linear relationships** between the enriched features.

       - **ARIMA (SARIMAX):** Leverages **statistical time-series dependencies** and directly utilizes the Macro indicators.

       - **LSTM (Deep Learning):** Uses a **Stacked, Bidirectional Architecture** with **Early Stopping** to effectively model long-term sequences and prevent overfitting.


### Data Acquisition and Exploration (EDA)

The project relies exclusively on local, cached data, ensuring reproducibility. The target variable for prediction is the Adjusted Close price.

  - A. Data Sourcing and Integrity
    - Tools Used: Data caching logic replaced direct API calls, relying on local CSV files for stock tickers and macro indicators (^VIX, SPY).
    - Data Cleaning: Dataframes were cleaned using backward-fill (bfill) and forward-fill (ffill) to impute missing values (due to market holidays) and a final dropna() ensures the time series is complete and aligned across all features.
    - Time Span: All models are trained on data from 2020-09-26 to 2025-09-26.

  - B. Visual and Statistical Findings
    Exploratory Data Analysis (EDA) confirmed key properties of the financial data:

    - Price Trends: Historical Price plots showed clear upward trends, confirming the data is non-stationary (a crucial input for the differencing component in ARIMA).

      - Visual Artifact:

![APPL Price Trends](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/AAPL_price_and_returns.png)
![GOOG Price Trends](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/GOOG_price_and_returns.png)
![MSFT Price Trends](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/MSFT_price_and_returns.png)
![TSLA Price Trends](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/TSLA_price_and_returns.png)

  - C. Returns Distribution: Returns distribution plots showed fat tails (high kurtosis) compared to a normal distribution, indicating the frequency of large price movements (market risk).

  - D. Correlation (Price vs. Macro): The Price vs. Macro Correlation Heatmap generally showed:

    - High positive correlation between the stock price and SPY (market index).
    - Moderate negative correlation between the stock price and VIX (volatility index).
![APPL Price and Macro Correlation](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/AAPL_price_macro_correlation.png)
![GOOG Price and Macro Correlation](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/GOOG_price_macro_correlation.png)
![MSFT Price and Macro Correlation](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/MSFT_price_macro_correlation.png)
![TSLA Price and Macro Correlation](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/TSLA_price_macro_correlation.png)

  - E. Correlation (Stock Returns vs. Macro Changes): Correlation between daily returns (price change) and macro changes was typically low, confirming that short-term stock movement is difficult to predict purely through simple linear relationships with macro factors.

### Feature Engineering Strategy
The predictive power of the models relies on a rich, multi-lag feature set calculated on each day prior to the 7-day forecast:

  - A. Multi-Lag Technical Features
  Technical features were calculated for three look-back periods (5, 20, and 60 days) to provide both short-term volatility and longer-term trend context:

| Lag Window                 | Feature                   | Insight Provided                              | 
|:------------------         |:------------              |----------------------------------------------:|
| Short-Term (5-Day)         | MA, Returns, Volatility   | Captures recent momentum and short-term noise.|
| Medium-Term (20- & 60-Day) | MA, Returns, Volatility   | Captures 1-month and 2-month trends, essential for smoothing out market noise.|

  - B. Feature Importance and Explainability
  Feature Importance plots revealed:
    - LR (Coefficients): Importance was heavily concentrated in the most recent Close Price and the longer-term Moving Averages, validating the trend-following nature of the linear model.
    - RF (Gini Importance): Importance was more broadly distributed across the multi-lag features and macro indicators, confirming the Random Forest's ability to utilize non-linear interactions among a diverse set of predictors.
  **Feature Importance Plots**
![APPL LR Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/AAPL_lr_feature_importance.png)
![GOOG LR Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/GOOG_lr_feature_importance.png)
![MSFT LR Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/MSFT_lr_feature_importance.png) 
![TSLA LR Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/TSLA_lr_feature_importance.png)

![APPL RF Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/AAPL_rf_feature_importance.png)
![GOOG RF Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/GOOG_rf_feature_importance.png)
![MSFT RF Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/MSFT_rf_feature_importance.png)
![TSLA RF Feature Importance Plot](https://github.com/vishwajitkumar47613/Stock_Prediction_Capstone_Part2/blob/main/eda_plots/TSLA_rf_feature_importance.png)

### Modeling and Evaluation
The models were evaluated using the robust WFV strategy, where the model is retrained every 7 days on an expanding history to simulate live trading.

 - A. Model Benchmarks and Methodologies

| Model                  | Type                    | Insight Provided             | Key Enhancement over LR baseline                          |
|:---------------------  |:--------                |:--------------------------   |:---------------------------------                         |
| Linear Regression (LR) | Linear/Statistical      | Walk-Forward Validation (WFV)| Baseline for comparison.                                  |
| Random Forest (RF)     | Non-Linear Ensemble     | Walk-Forward Validation (WFV)| Captures non-linear feature interactions and dependencies.|
| ARIMA (SARIMAX)        | Statistical Time-Series | Walk-Forward Validation (WFV)| Explicitly models non-stationarity and uses macro indicators as Exogenous Variables.
| LSTM                   | Deep Learning / Sequence| Static 80/20 Split           | Uses Stacked Bidirectional Layers and Early Stopping to model long-term sequence dependency.|

- B. **Key Findings and Model Performance**
   - **The Walk-Forward Validation** yielded strong evidence that model complexity does not guarantee better performance in financial forecasting.
   - **The ARIMA model**, leveraging stationarity and exogenous macro features, proved superior in predicting short-term price movements across all stocks.
   - The poor performance of the **LSTM model** suggests it was either overfitting due to its complexity or suffered from insufficient retraining (only retrained once vs. WFV models retrained dozens of times).
   - Although **the RF model** may not be the best for MAPE, it demonstrates consistent performance across all stocks, including TSLA, which is the most volatile among them.
   - Implementing **Walk-Forward Validation (WFV)** instead of a single 80/20 split significantly improved the MAPE score of the LR model compared to the baseline LR MAPE established in Capstone Project Part 1.

| Ticker   | Best Model (Lowest MAPE)   |   ARIMA MAPE | LR  MAPE | RF MAPE | LSTM MAPE |
|:---------|:---------------------------|--------------|---------:|--------:|----------:|
| AAPL     | ARIMA                      |   1.71%      |   2.88%  | 4.06%   | 19.83%    |
| GOOG     | ARIMA                      |   1.69%      |   2.94%  | 4.08%   | 36.06%    |
| MSFT     | ARIMA                      |   1.24%      |   2.37%  | 3.32%   | 23.54%    |
| TSLA     | ARIMA                      |   3.62%      |   7.11%  | 3.61%   | 36.63%    |



