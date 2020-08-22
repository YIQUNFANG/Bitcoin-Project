# Bitcoin-Project
Machine learning-- Bitcoin Price Prediction 

# Can we train a model to predict the BTC close price 30 days into the future?

Bitcoin is a digital currency created in January 2009 following the housing market crash. Over the course of bitcoin's history, it has undergone rapid growth to become a significant currency both on and offline. In this project, we are going to train some models to do prediction about Bitcoin price.
The data used for the project is drawn from Kaggle website which includes the various daily bitcoin prices in the stock and 3 daily financial factors for the years 2012 to 2020. This data appears in time series format with the intervals of one minute. The dataset can be found here: https://www.kaggle.com/mczielinski/bitcoin-historical-data

### Dataset Description & Exploratory
There are totally 4,363,457 records in which 28.35% of them are null data, leaving 3,126,480 valuable records for us to conduct our analysis.

The attributes consists of:

One ordinal attribute i.e. Timestamp, which is in Unix epoch date format with the interval on every 60 seconds 7 Numeric attributes including

* Open: Open price at start time window
* High: High price within time window
* Low: Low price within time window
* Close: Close price at the end of time window
* Volume_(BTC): Amount of BTC transacted in time window
* Volume_(Currency): Amount of Currency transacted in time window
* Weighted_Price: volume-weighted average price (VWAP)

After excluding all null data from this dataset, there remains no additional missing data in the entire dataset which saved us a lot of work for data preprocessing.
Because the original dataset has only six attributes and those attributes are very similar and highly related, and the open price, close price and weighted price are almost equal, we introduced new attributes that might have influence on Bitcoin price from Yahoo Finance, including Gold Price, volatility index, and S&P 500 and Oil price.

### Techniques
Apart from the new attributes we introduced from the external dataset, we also created a new column, BTC price in 30 days by shifting the existing BTC price column. Time Periods are from Dec 1st 2017 through July 30th 2020. The target column is BTC price in 30 days. The features we have:

* Gold price
* Volatility Index
* S&P 500
* Oil Price
* BTC Transaction Volume
* BTC price
To solve this problem, we use the linear regression model to identify the relationship between BTC price in 30 days and other attributes. In addition, ridge regression and lasso regression are used to do the feature selection. Moreover, we use the grid search library for tuning the hyperparameter.
