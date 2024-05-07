**Introduction**
Non-professional investors often try to find an interesting stock among those in an index. In practical terms, people like to find the best stocks to buy from an index and wait a few days hoping to get an increase in the price of this investment.
We aim to implement and find the modelling techniques that can be used to predict the price of the stock in the short term (one day, one week and 14 days).

**Objective**
Analyzing historical stock data for Microsoft and predicting the short-term future stock price.

**Strategy**
We have used multiple techniques for the analysis and predictions of the Microsoft stock price using

1.	Non-Time Series modelling with Feature Engineering: 
•	Random Forest: We added lag 1 differencing as a feature and used Open, High, Low, Volume and lag1 (representing trend) to run Random Forest to create a model similar to the linear model and square of trend model in time series. 

2.	Time Series Models: 
•	Linear, Square, 3rd Power and 4th Power Trend
•	SARIMA 
•	LSTM

**Exploratory Data Analysis**
1)	Trend and Seasonality: In a time series, the trend component represents the long-term movement or pattern in the data.
It captures the underlying direction or tendency of the data over time, ignoring short-term fluctuations, seasonality, and noise. Microsoft stock exhibits an overall increasing trend except for large dips in Covid period and the year 2023. There is no seasonality exhibited.
Figure 1: Stock price from year 2019 to 2024
Figure 2: Seasonality (Stock price from year 2019 to 2024)

3)	Volatility: Volatility is a measure of the variability or dispersion of returns, indicating the degree of fluctuation in the stock price. Microsoft stock exhibits high volatility or significant trends over short periods, such as two years as shown in Figure 2 below which shows daily deviation or fluctuation in the stock price.
Figure 3: Standard Deviation of Daily Returns (Closing Price)
From the plots we see that the sharp decline in the price trend and the big dip in the daily stock value in the year 2020 due to Covid-19 is an anomaly.
Since a pandemic is a very rare scenario, we have chosen to focus on analyzing the stock price from the beginning of 2021 to 2024 as the daily stock price fluctuation shows stationarity and no seasonality.


**Models:**
Comparison of RMSE values for all models

**Conclusion**
We have implemented multiple models to compare their performance to predict time-series stocks data. The findings so far with the models completed are:
Linear Model performed better with a non-linear Trend function. This supports our observation from our plot: No linear relationship seen in the trend of Stock Price.
SARIMA p and q values from the ACF and PACF charts did not yield the best performance. We got better model with hyperparameter tuning and adding seasonality.
Even if Linear Model performed well, we don’t know what kind of non-linearity will be present in the data for other Stocks.
LSTM: LSTM results show low mean square errors and predicted values following the actual values very closely. LSTM is also scalable.

**Next Steps**
Random Forest may be improved by adding more relevant features like Moving Averages or industry specific metrics.
Increasing the scope of Data for multiple Tickers(companies) and test the performance
Taking events into account when modelling






