# Effect-of-News-on-Stock-Returns-A-Regression-Neural-Network-Approach

This project aims to compare the performance of a stock return prediction model with or without the use of news features.

Section 2.1 talked about the two data sources, one is the stock-related news data found on Kaggle.com; the other is the stock data retrieved from WRDS, given the assets mentioned in the first data source. The trading period we are looking at is from 2013-01-01 to 2016-12-31. Since the original datasets are too large, I extracted a sample that contains 100 randomly selected assets, and made sure that each of them has at least 1,000 data points in the final dataset we are used for training and testing.

Section 2.2 talked about the model used, which is a regression NN model with a few Dense Layers, BatchNormalization Layers, and Dropout Layers. Also, I used an embedding layer to process a unique feature among the others, assetCode. It is believed that this layer is important for the model to distinguish one asset from another. The details of the model used can be found below.
