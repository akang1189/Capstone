
# Stock Prediction using Time Series and Neural Networks



**Problem Statement:** 

Problem Description

The U.S. Stock Market has long been a symbol for capitalism, where some may argue a strong market correlates to a successful economy. However in recent times, with the rise of automated trading and technology, how come none of the brightest minds has been able to "beat the market"? Today we will try and answer that question, more specifically, can we accurate forecast and predict future stock prices using Machine Learning and Neural Networks. We will focus on fundamental financial data however it is important to note, stock prices are notoriously volatile and very difficult to predict with a high degree of accuracy. Machine learning techniques will help us to catch patterns and any new insights we wouldn't normally be able to see with the "human eye". We hope to add some additional features in the future(Sentiment Analysis, 3D chart image data, Quantifiable socio-economic factors, Quantifiable psychological and behavioral factors).

***
***


### Table of Contents

Executive Summary


******
Today we will be looking at historical data of the stock ticker SPY, an ETF tracking the S&P500 index. We will build a multivariate neural network to predict the future price of this stock.  
************

Data Import
Data Cleaning
Modeling
Results
Conclusions

***
***


### Data
**Description:**

Data Import
Yahoo! Finance (yfinance) discontinue their historical stock data API however yfinance has since stepped in as a reliable replacement for the information we need. Intraday stock data was limited to 60 days so we used daily historic data from 01-29-1993 (first day of trading) to 8-13-21 (present). 
https://pypi.org/project/yfinance/

Ticker= 'SPY'
First traded on the American Stock Exchange (AMEX) on January 29, 1993,
https://www.sec.gov/Archives/edgar/data/1222333/000119312513023294/d473476dfwp.htm


Train/Test/Val Split (80/15/5)

MinMaxScaler

Split_sequences to account for sequential time series data input/output


Data Cleaning and Feature Engineering

Remove weekends and non trading days.

Added Column

 'totalAssets': 374031319040,
 'yield': 0.012999999000000002,
 'trailingAnnualDividendYield': 0.01256664,
 'trailingAnnualDividendRate': 5.563,
 'trailingPE': 3.079496,
 'fiftyTwoWeekHigh': 443.882,
 'fiftyTwoWeekLow': 319.8,
 'regularMarketVolume': 44034340,
 'averageVolume': 63724817,
 'averageDailyVolume10Day': 47701200,
 'threeYearAverageReturn': 0.17830000000000001,
 'fiveYearAverageReturn': 0.17320000000000002,
 'twoHundredDayAverage': 411.22543,
 'fiftyDayAverage': 434.7441,


200/50/30/20 dayMoving Average


***


### Model

**Description:**


Long Short Term Memory (LSTM)

CNN (CNN-1D)

CNN + LSTM


# Hyperparameters
timesteps = 3/5/10/20/50/200
hl = [100,10]
lr = 0.0005
batch_size = 10/32/64/100
num_epochs = 10/100


***

## VI) Results

The experiments were done for four deep learning models we have
trained. The models are cross validated on a window size of 600 records
and 5 splits. The final results obtained are shown in Table 1 below.

** Table 1: Results of different models on test data **

| Model | MSE |
|---|---|
| LSTM | 0.00055 |
| CNN |  3.1033E-12 |
| CNN-LSTM | -4.88E-11 |

CNN has the lowest MSE (MSE – 3.1033E-12) while LSTM has the highest. (MSE – 0.00055)

CNN/LSTM falls just short of CNN and in between CNN/LSTM (MSE – 4.88-11)


**Next Steps**
Graph images in 2-D layer CNN
Sentiment analysis from News source // Social Media // Stock Screeners
More Data and Feature Engineering

Intra-Day minute interval model
Build Automated trading program based on prediction models
Add more feature engineering
Add Options Activity
Add Sentiment Analysis (Social Media and News Sources)
traditional data + new feature engineering correlations
volume/futures
-social influencers
-satellite imagery predictions on weather? food prices?

