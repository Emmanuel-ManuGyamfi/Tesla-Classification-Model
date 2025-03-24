# Predicting Tesla (TSLA) Stock Price Movement

## Overview
The goal of the project is to create a predictive model that forecasts Tesla stock price movements based on historical market data and various financial indicators. By using machine learning techniques, the model classifies whether the stock price will increase or decrease on the following trading day. The final XGBoost model performed with 65.5% accuracy and 65.2% F1 score.

## Business Understanding
Stock market movements are influenced by multiple factors, including past price trends, market sentiment, and economic indicators. Tesla stocks has seen a lot of price movement recently. With frequent price swings and high investor interest, predicting Tesla's short-term stock movements presents both challenges and opportunities. 

## Data Understanding 
The Tesla and Market Data came from **[Yahoo Finance - Tesla Historical Data](https://finance.yahoo.com/quote/TSLA/history/)**. The Macroeconomic indicators data came from **FRED - (https://fred.stlouisfed.org/series)** The data consisted of approximately 3.8k dates from when Tesla was first listed on the stock market in 2010 and over 70 features to begin with. The price movement of the Tesla stock is fairly balanced over this time, almost an even split. The pie chart below shows the breakdown of the daily Tesla stock price movement whether the price increased that day or decreased. 

![image](https://github.com/user-attachments/assets/b2eb1809-4fb7-4c3d-96a3-fa92e76039a4)

## EDA - Analysis, Feature Engineering, Feature Selection and Visualisations
The chart below illustrates Tesla's historical stock price movements, highlighting key price levels:

- **Blue Line**: Tesla's closing stock prices over time.
- **Red Dashed Line**: Tesla's all-time high price ($479.86).
- **Green Dashed Line**: Tesla's closing price on the most recent trading day ($248.71 on 2025-03-21).

![image](https://github.com/user-attachments/assets/a11b24ad-5875-494f-9ab5-a2010f11d3fe)

Feature engineered a number of economic indicators 
#### Creating Economic Technical Indicators
* **SMA** (**Simple Moving Average**): The average closing price over a set period (e.g., 5 or 10 days) to smooth out price fluctuations and identify trends.

* **EMA** (**Exponential Moving Average**): A weighted moving average that gives more importance to recent prices, making it more responsive to price changes than SMA.

* **Bollinger Bands** (Upper & Lower Band): A volatility indicator consisting of a 20-day moving average (SMA) and two standard deviation bands, where wider bands indicate higher volatility.

* **RSI** (**Relative Strength Index**, 14-day): A momentum indicator (0-100 scale) that measures whether a stock is overbought (>70) or oversold (<30).

* **ATR** (**Average True Range**, 14-day): A volatility indicator that measures the average range between high and low prices over 14 days.

* **MACD** (**Moving Average Convergence Divergence**): A trend-following indicator that calculates the difference between the 12-day and 26-day EMAs to identify potential buy/sell signals.

* **MACD Signal Line**: A 9-day EMA of the MACD that helps confirm trend changes when crossed by the MACD line.

* **ROC** (**Rate of Change**, 14-day): A momentum indicator that shows the percentage change in price over the last 14 days, indicating strength or weakness in the trend.
