------------------------- 
Tags: #ml  #tsa 
⏰ Date Created:  2023-09-06, @ 09:37

---
>[!info] Keywords
>* Trend, Noise, Season, Cycle
>* Interpolation VS Extrapolation
>* Stationary Data vs Non Stationary Data
>* ARIMA, SARIMA, SARIMX, LSTM
>* Univariate Vs Multivariate

### Key Terms:

1. **Trend:**
    
    - The trend component represents the long-term movement or direction in a time series. It captures the underlying pattern or tendency in the data.
    - Trends can be upward, indicating a gradual increase over time, downward, indicating a decrease, or flat, where there is no significant change.
    - Identifying and modelling the trend is essential for understanding the overall growth or decline in the data. Trend analysis can involve various statistical techniques, such as moving averages or regression analysis.

![trend](https://www.section.io/engineering-education/univariate-time-series-using-facebook-prophet/trends.png)

2. **Seasonality:**

Think of seasonality like a repeating pattern in your data that happens regularly, just like the changing seasons of the year. In time series analysis, this pattern repeats at fixed intervals, such as every week, month, or year.

Imagine you're looking at the sales of ice cream. You'd expect to see a rise in sales every summer and a drop in winter, right? That's a seasonal pattern because it happens predictably with the seasons. In this case, summer is the "high season," and winter is the "low season" for ice cream sales.
[[naive forecasting]] : In general, naive forecasting means copying the latest known value due to strong repetitive seasonality.  

3. **Cycle:**

Now, think of a cycle as a more extended, but not as predictable, pattern in your data. It's like a longer wave that goes up and down, but it doesn't have a strict schedule like seasonality.

Let's say you're studying the real estate market. Prices might go up for a few years due to a strong economy, then down for a few years due to a recession. This up-and-down movement is a cycle. It's not as regular as seasonality, and it doesn't follow a strict calendar, but it still has a noticeable pattern over a more extended period.

$$ Cycle = Seasonality + Noise$$

So, in simple terms:

- **Seasonality** is like a regular, predictable pattern that happens at fixed intervals (e.g., every year, month, or week).
- **Cycle** is a more extended pattern that goes up and down but doesn't follow a strict schedule like seasonality.

4.  **Noise (Irregular Component):**
    
    - The noise component, also known as the irregular component or error term, represents the random fluctuations and unexplained variations in a time series that cannot be attributed to the trend, cycle, or seasonality.
    - Noise can result from various sources, including measurement errors, unforeseen events, or other factors that are not captured by the model.
    - Analyzing and modeling the noise component helps in assessing the goodness-of-fit of a time series model and understanding the uncertainty in predictions.
------
### Time Series Analysis:

Time series analysis is a specialized field within machine learning and statistics that focuses on **understanding and predicting data points collected or recorded over time**. Time series data is characterised by its temporal dependencies, meaning that the **order of observations** matters, and each data point is associated with a specific time or sequence index. 

**1. Temporal Nature:**

- Time series data is inherently sequential, where each data point is collected at **successive** time intervals. Traditional machine learning models, on the other hand, assume that data points are independent and identically distributed (i.i.d.), making them unsuitable for time-dependent data.

**2. Time Dependency:**

- Time series analysis explicitly considers the temporal dependencies between data points. This means that the value at a specific time step can depend on previous time steps. Traditional machine learning models don't capture this temporal aspect, making them ill-suited for tasks like forecasting stock prices, predicting weather, or analysing physiological data.

**3. Autocorrelation:**

- In time series data, there is often autocorrelation, which means that a data point's correlation with previous data points can be significant. Time series models are designed to capture this autocorrelation, which is crucial for accurate predictions. Traditional ML models typically assume that data points are independent, which can lead to poor performance on time series data.

**4. Stationarity:**

- Time series analysis often requires dealing with non-stationary data, where statistical properties change over time. Traditional ML models assume stationarity and may not perform well when the data violates this assumption. Time series models can account for and model non-stationary patterns.
[[Stationary Vs Non Stationary Data]]

**5. Feature Engineering:**

- In traditional machine learning, feature engineering plays a significant role in model performance. However, in time series analysis, feature engineering can be more challenging due to the temporal nature of the data. Time series models often require specialized feature engineering techniques such as lag features, rolling statistics, and time-based transformations.

**6. Model Selection:**

- Time series analysis typically involves specialized models like Autoregressive Integrated Moving Average (ARIMA), Exponential Smoothing methods, Seasonal Decomposition, or more modern approaches like Recurrent Neural Networks (RNNs), Long Short-Term Memory (LSTM) networks, and Prophet. These models are specifically designed to capture time-dependent patterns. In contrast, traditional ML models include decision trees, random forests, and support vector machines, which are not inherently designed for time series data.

**7. Evaluation Metrics:**

- Evaluation metrics for time series models often include Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and more specialized metrics like AIC, BIC, or information criteria. These metrics account for the temporal aspect of the data and are different from traditional ML evaluation metrics like accuracy, precision, and recall.

In summary, time series analysis is a specialized branch of machine learning tailored for data with temporal dependencies. It differs from traditional ML by considering the sequential nature of data, capturing autocorrelation, handling non-stationarity, using specialized models, and employing unique evaluation metrics. Understanding the differences between these two approaches is crucial for effectively analyzing and modeling time series data.

--------
### [[ARIMA]]
### [[SARIMA]]
### [[SARIMAX]]

---
### Interview Questions:

1. Can we solve times series related problem using Linear regression?
	NO, because of difference in [[Interapolation Vs Extrapolation]]

1. 


>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
