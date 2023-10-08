
#tsa #ml 
**Stationary Data:**

1. **Constant Mean:** In a stationary time series, the mean (average) of the data remains constant over time. This implies that, on average, there are no long-term trends or systematic shifts in the data.
    
2. **Constant Variance:** The variance (or standard deviation) of the data also remains constant throughout the time series. This means that the spread or dispersion of data points around the mean does not change over time.
    
3. **Constant Autocovariance:** Autocovariance is a measure of the linear relationship between data points at different time lags. In stationary data, the autocovariance is the same for all time lags, indicating that the relationship between data points does not depend on when they occur.
    
4. **No Seasonality:** Stationary data does not exhibit any seasonality, which means there are no recurring patterns or cycles that repeat at fixed intervals.
    
5. **Statistical Tests:** Stationarity can be tested using statistical tests such as the Augmented Dickey-Fuller (ADF) test or the Kwiatkowski-Phillips-Schmidt-Shin (KPSS) test. These tests help confirm whether a time series is stationary or not.
    

**Non-Stationary Data:**

1. **Changing Mean:** In non-stationary data, the mean of the time series changes over time. This implies the presence of trends, shifts, or other systematic patterns in the data.
    
2. **Changing Variance:** The variance of non-stationary data is not constant. It can increase or decrease over time, indicating changing volatility.
    
3. **Changing Autocovariance:** Non-stationary data often exhibits autocovariance that depends on the time lag. This means that the linear relationship between data points varies with time, making it challenging to make predictions.
    
4. **Seasonality:** Non-stationary data can have seasonality, which means that there are recurring patterns or cycles at fixed intervals. Seasonal components introduce dependencies that need to be modeled separately.
    
5. **Statistical Tests:** Non-stationary data typically fails statistical tests for stationarity, such as the ADF or KPSS tests.
    

**Why Stationarity Matters:**

Stationarity is a critical assumption for many time series models, including traditional ones like [[ARIMA]] (AutoRegressive Integrated Moving Average) and newer ones like [[LSTM]] (Long Short-Term Memory) networks. When dealing with non-stationary data, it is often necessary to transform the data to make it stationary before applying these models.

Common techniques for achieving stationarity in non-stationary data include differencing (subtracting a lagged version of the time series from itself), log transformations, or seasonal decomposition. Once data is stationary, it becomes easier to model and make predictions because the statistical properties are more consistent over time.

In summary, **the main difference between stationary and non-stationary data lies in the constancy of statistical properties such as mean, variance, and autocovariance over time.** Stationary data has constant properties, while non-stationary data exhibits changing properties, which can complicate the modeling and analysis of time series data.

### Further Reading

[[Augmented Dickey–Fuller test]]
