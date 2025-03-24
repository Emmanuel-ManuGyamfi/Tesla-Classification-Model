# Predicting Tesla (TSLA) Stock Price Movement

https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.edigitalagency.com.au%2Flogos%2Fnew-tesla-logo-red-png%2F&psig=AOvVaw0gJZTbq6lIH1OrfE3ms4MT&ust=1742941707827000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCJiE6fzho4wDFQAAAAAdAAAAABAQ![image](https://github.com/user-attachments/assets/e70f2643-a3c5-41cf-8856-462a5497fda5)

## Overview
The goal of the project is to create a predictive model that forecasts Tesla stock price movements based on historical market data and various financial indicators. By using machine learning techniques, the model classifies whether the stock price will increase or decrease on the following trading day. The final XGBoost model performed with 65.5% accuracy and 65.2% F1 score.

## Business Understanding
Stock market movements are influenced by multiple factors, including past price trends, market sentiment, and economic indicators. Tesla stocks has seen a lot of price movement recently. With frequent price swings and high investor interest, predicting Tesla's short-term stock movements presents both challenges and opportunities. 

## Data Understanding 
The Tesla and Market Data came from **[Yahoo Finance - Tesla Historical Data](https://finance.yahoo.com/quote/TSLA/history/)**. The Macroeconomic indicators data came from **FRED - (https://fred.stlouisfed.org/series)** The data consisted of approximately 3.8k dates from when Tesla was first listed on the stock market in 2010 and over 70 features to begin with. The price movement of the Tesla stock is fairly balanced over this time, almost an even split. The pie chart below shows the breakdown of the daily Tesla stock price movement whether the price increased that day or decreased. 

![image](https://github.com/user-attachments/assets/b2eb1809-4fb7-4c3d-96a3-fa92e76039a4)

## Feature Engineering
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

## Exploratory Data Analysis
Visualised trends, identified patterns, and understood correlations between features for feature selection.

The chart below illustrates Tesla's historical stock price movements, highlighting key price levels:

- **Blue Line**: Tesla's closing stock prices over time.
- **Red Dashed Line**: Tesla's all-time high price ($479.86).
- **Green Dashed Line**: Tesla's closing price on the most recent trading day ($248.71 on 2025-03-21).

![image](https://github.com/user-attachments/assets/a11b24ad-5875-494f-9ab5-a2010f11d3fe)

## Feature Selection 
To enhance the model's performance, a **correlation matrix** was used to identify highly correlated features. Features that had strong multicollinearity were considered redundant and removed. 

- **Before Feature Selection**: The dataset contained **71** features, leading to potential overfitting and redundancy.
- **After Feature Selection**: The number of features was reduced to **12**, ensuring that only the most informative variables were retained for model training.

The correlation matrix below shows a number of highly correlated features.

![image](https://github.com/user-attachments/assets/a2e6ceeb-cec0-4bb5-abbe-1313148c8933)

## Modelling and Evaluation 

Compared multiple classification models (e.g., Logistic Regression, Random Forest, XGBoost) and select the best-performing one. The champion model was XGBoost with the score metrics in the below table 

![image](https://github.com/user-attachments/assets/2a5d9ad5-0ed9-4549-909f-37409146f24b)

F1 score final XGB model:  0.652542372881356

Recall score final XGB model:  0.6567164179104478

Precision score final XGB model:  0.6484210526315789

Accuracy score final XGB model:  0.6554621848739496

The below plot shows that MACD, RS1 14 and Volume_^DJI(Trading volume of Dow Jones Industrial Average) were the Top 3 most important factors in determining whether the Tesla Stock Price will Increase or Decrease for that trading day. The overall model performed with 65.5% accuracy and 65.2% F1 score. 

![image](https://github.com/user-attachments/assets/eb78f37d-8474-44fd-9f29-2d72031dbae3)

Below is a table of the model results so far predicted and actual 

<img width="222" alt="image" src="https://github.com/user-attachments/assets/4be48693-6578-4926-96af-95da1e7f9416" />

**Latest Prediction**

Prediction: Tesla's stock price is expected to INCREASE tomorrow with 82.33% confidence.

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Predicted_Label</th>
      <th>Actual_Label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2025-03-24</td>
      <td>1</td>
      <td>None</td>
    </tr>
  </tbody>
</table>
</div>

## Conclusion 

This project successfully demonstrates the potential of machine learning in predicting Tesla's stock price movements. The model provides a data-driven approach to stock price forecasting, helping investors and analysts make informed decisions.

However, stock prices are influenced by multiple external factors such as market news, economic changes, and global events, which are not always captured in historical data. Future improvements, such as adding sentiment analysis, implementing deep learning models (e.g. LTSM) and enhanced feature engineering, could further improve prediction accuracy and adaptability to market trends.

## Installation

Clone this repository:

git clone https://github.com/emmanuel-mgyamfi/tesla-classification-model.git
cd tesla-classification-model

Install the required dependencies:

pip install -r requirements.txt

## Technologies Used

Python 3.11

Pandas

NumPy

Scikit-learn

XGBoost

Matplotlib / Seaborn

## Usage

Run the following command to train the model:

python train_model.py

For Jupyter Notebook users:

jupyter notebook
# Open tsla_classification_model.ipynb



