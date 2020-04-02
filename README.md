# Prediction model for Bitcoin based on historical prices and other features

## 1- Data Gathering and Analysis

- Identify a source for BTC prices (Jan 1, 2010, to June 30, 2019) along with the following additional data fields

a. BTC transaction volume\
b. BTC price volatility\
c. BTC miner revenue\
d. Amount of Bitcoin core paid to miners in fees
e. Prices for other cryptocurrencies

## 2 -  Data Pre-processing for Models

For the modeling part, define the following time periods for train, test and validation:

Train: Jan 1, 2010 - June 30, 2018\
Validation: July 1, 2018 - Dec 31, 2018\ 
Test: Jan 1, 2019 - June 30, 2019

At each date, you have to lookback 28 days and make a prediction for the next 7 days. For example for a prediction date of March 28, you have to look at historic data and features from March 1-28 (28 days), and use it to make a prediction for March 29-April 4 (7 days).

In this manner, using a moving window of 28+7 = 34 days, you can generate your lookback features and target in each of your train, validation, and test datasets

## 3 - Build and Train Models

Use mean absolute error (MAE) as metric of choice:

- Build 2 simple benchmark predictions, and calculate MAE for the following on the validation set:

  a. Use an average (e.g. prediction for each target period is an average of the BTC prices in the lookback period)\
  b. Use the last value (e.g. prediction for each target period is the most recent BTC price in the lookback period)

- Build NN, RNN models with LSTM and GRU layers
- Build time series model(ARIMA)

## 4 - Evaluation

- Evaluate each of the models in Part 3 on the test set, calculate MAE and RMSE 
