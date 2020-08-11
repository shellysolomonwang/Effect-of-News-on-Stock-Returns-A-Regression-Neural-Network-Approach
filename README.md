# Effect-of-News-on-Stock-Returns-A-Regression-Neural-Network-Approach

This project aims to compare the performance of a stock return prediction model with or without the use of news features.

# Data Preprocessing
Section 2.1 talked about the two data sources, one is the stock-related news data found on Kaggle.com; the other is the stock data retrieved from WRDS, given the assets mentioned in the first data source. The trading period we are looking at is from 2013-01-01 to 2016-12-31. Since the original datasets are too large, I extracted a sample that contains 100 randomly selected assets, and made sure that each of them has at least 1,000 data points in the final dataset we are used for training and testing.

1. Stock-related News Data from Kaggle Competetion (https://www.kaggle.com/c/two-sigma-financial-news/data) with variables including:
- Date
- Asset Code (Ticker)
- Headline (Textual Data)
- Relevancy Info (Numerical Data)
- Sentiment Info (Numerical Data)
- News Artical Info (Numerical Data)
- Time Effect of News counted by Novelty (Numerical Data)
- Time Effect of News counted by Trading Volume (Numerical Data)

2. Stock Price Data downloaded from WRDS (Compustat - Capital IQ) , using the ticker derived from the cleaned News Dataset. The features of interest include:
- Date
- Asset Code (Ticker)
- Volume
- Open Price
- Close Price
From these variables, I calculated the following stock returns for stock return prediction:
returnsClosePrev1 - 1-day stock return calculated by closing price
returnsOpenPrev1 - 1-day stock return calculated by open price
returnsClosePrev10 - 10-day stock return calculated by closing price
returnsOpenPrev10 - 10-day stock return calculated by open price
returnsOpenNext10 - 10-day forward stock return calculated by open price - this will be the target variable for the regression model

# Model
Section 2.2 talked about the model used, which is a regression NN model with a few Dense Layers, BatchNormalization Layers, and Dropout Layers. Also, I used an embedding layer to process a unique feature among the others, `assetCode`. It is believed that this layer is important for the model to distinguish one asset from another. The details of the model used can be found below.
