# Predicting Tesla (TSLA) Stock Price Movement

## Overview
The goal of the project is to create a predictive model that forecasts Tesla stock price movements based on historical market data and various financial indicators. By using machine learning techniques, the model classifies whether the stock price will increase or decrease on the following trading day. The final XGBoost model performed with 65.5% accuracy and 65.2% F1 score.

## Business Understanding
Stock market movements are influenced by multiple factors, including past price trends, market sentiment, and economic indicators. Tesla stocks has seen a lot of price movement recently. With frequent price swings and high investor interest, predicting Tesla's short-term stock movements presents both challenges and opportunities. 

## Data Understanding 
The Tesla and Market Data came from **[Yahoo Finance - Tesla Historical Data](https://finance.yahoo.com/quote/TSLA/history/)**. The Macroeconomic indicators data came from **FRED - (https://fred.stlouisfed.org/series)** The data consisted of approximately 3.8k dates from when Tesla was first listed on the stock market in 2010 and over 70 features to begin with. The price movement of the Tesla stock is fairly balanced over this time, almost an even split. 

            ![image](https://github.com/user-attachments/assets/b2eb1809-4fb7-4c3d-96a3-fa92e76039a4)
