
https://en.wikipedia.org/wiki/Augmented_Dickey%E2%80%93Fuller_test

**Purpose**:

The Augmented Dickey-Fuller test is a statistical hypothesis test used in time series analysis to determine whether a given time series is stationary or not. Stationarity is an important concept in time series analysis, and it means that the statistical properties of a time series, such as its mean, variance, and autocorrelation, do not change over time. In simpler terms, a stationary time series has a constant statistical behavior, making it easier to model and make predictions.

**Concept Behind the ADF Test**:

The ADF test is based on the null hypothesis (H0) and the alternative hypothesis (H1):

- **Null Hypothesis (H0)**: The time series data is non-stationary. In other words, it has a unit root, which means it has a time-dependent structure.
    
- **Alternative Hypothesis (H1)**: The time series data is stationary. It does not have a unit root, and its statistical properties are constant over time.
    

The ADF test calculates a test statistic (ADF statistic) and compares it to critical values at a certain significance level. The critical values depend on the sample size and the chosen significance level. The ADF statistic measures how strongly the time series data deviates from stationarity. If the ADF statistic is smaller than the critical values, you reject the null hypothesis (H0) and conclude that the data is stationary. Otherwise, if the ADF statistic is greater than the critical values, you fail to reject the null hypothesis, indicating that the data is non-stationary.

Here's a simplified interpretation of the results:

- If ADF statistic < Critical values: You have evidence to believe that the data is stationary, and you can proceed with time series analysis or modeling.
    
- If ADF statistic >= Critical values: You do not have enough evidence to conclude that the data is stationary, suggesting that further differencing or transformations might be needed to achieve stationarity.
    

In your code, `adfuller(stock_data["Close"])` computes the ADF statistic for the "Close" price data of a stock. By running this test, you can assess whether the stock price series is stationary or not. If it is stationary, you may proceed with various time series analysis techniques, such as ARIMA modeling, forecasting, or other statistical analyses. If it's non-stationary, you may need to apply differencing or other transformations to make it stationary before modeling.

### Practical Intuition 
```python
from statsmodels.tsa.stattools import adfuller
```

```python
# Test for Stationary:

def testStationary(timeseries):

# determining rolling statistics

rolmean = timeseries.rolling(365).mean() #rolling mean

rolstd = timeseries.rolling(365).std() #rolling standard deviation

  

# plot rolling statistics:

plt.figure(figsize=(18,8))

plt.grid("both")

plt.plot(timeseries, color= "blue", label="Original", linewidth=3)

plt.plot(rolmean, color= "red", label="Rolling Mean", linewidth= 3)

plt.plot(rolstd, color= "green", label="Rolling std", linewidth= 4)

plt.legend(loc="best", fontsize=20, shadow = True, facecolor = "lightpink", edgecolor = "k")

plt.title("Rolling mean and Standard Deviation", fontsize=25)

plt.xticks(fontsize = 15)

plt.yticks(fontsize = 15)

plt.show()

  

print("Result of dickey Fuller Test")

adft = adfuller(timeseries, autolag="AIC")

# output for adft will give us without defining what the values are.

# hence we manually write what values does it explains using a for loop.

output = pd.Series(adft[0:4], index = ["Test Statistics", "p-values", "No of lags used", "NO of observations used"])

  

for key, values in adft[4].items():

output['critical value(%s)'%key] = values

print(output)
```

![[Pasted image 20230915120600.png]]

```output:
Result of dickey Fuller Test 
Test Statistics 1.400069 
p-values 0.997114 
No of lags used 18.000000 
NO of observations used 2397.000000 
critical value(1%) -3.433081 
critical value(5%) -2.862747 
critical value(10%) -2.567412 
dtype: float64
```
