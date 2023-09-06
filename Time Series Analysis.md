------------------------- 
Tags: #ml  
⏰ Date Created:  2023-09-06, @ 09:37

---
>[!info] Keywords
>* 
>* 

Time series analysis is a specialized field within machine learning and statistics that focuses on **understanding and predicting data points collected or recorded over time**. Time series data is characterised by its temporal dependencies, meaning that the **order of observations** matters, and each data point is associated with a specific time or sequence index. 

**1. Temporal Nature:**

- Time series data is inherently sequential, where each data point is collected at **successive** time intervals. Traditional machine learning models, on the other hand, assume that data points are independent and identically distributed (i.i.d.), making them unsuitable for time-dependent data.

**2. Time Dependency:**

- Time series analysis explicitly considers the temporal dependencies between data points. This means that the value at a specific time step can depend on previous time steps. Traditional machine learning models don't capture this temporal aspect, making them ill-suited for tasks like forecasting stock prices, predicting weather, or analyzing physiological data.

**3. Autocorrelation:**

- In time series data, there is often autocorrelation, which means that a data point's correlation with previous data points can be significant. Time series models are designed to capture this autocorrelation, which is crucial for accurate predictions. Traditional ML models typically assume that data points are independent, which can lead to poor performance on time series data.

**4. Stationarity:**

- Time series analysis often requires dealing with non-stationary data, where statistical properties change over time. Traditional ML models assume stationarity and may not perform well when the data violates this assumption. Time series models can account for and model non-stationary patterns.

**5. Feature Engineering:**

- In traditional machine learning, feature engineering plays a significant role in model performance. However, in time series analysis, feature engineering can be more challenging due to the temporal nature of the data. Time series models often require specialized feature engineering techniques such as lag features, rolling statistics, and time-based transformations.

**6. Model Selection:**

- Time series analysis typically involves specialized models like Autoregressive Integrated Moving Average (ARIMA), Exponential Smoothing methods, Seasonal Decomposition, or more modern approaches like Recurrent Neural Networks (RNNs), Long Short-Term Memory (LSTM) networks, and Prophet. These models are specifically designed to capture time-dependent patterns. In contrast, traditional ML models include decision trees, random forests, and support vector machines, which are not inherently designed for time series data.

**7. Evaluation Metrics:**

- Evaluation metrics for time series models often include Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and more specialized metrics like AIC, BIC, or information criteria. These metrics account for the temporal aspect of the data and are different from traditional ML evaluation metrics like accuracy, precision, and recall.

In summary, time series analysis is a specialized branch of machine learning tailored for data with temporal dependencies. It differs from traditional ML by considering the sequential nature of data, capturing autocorrelation, handling non-stationarity, using specialized models, and employing unique evaluation metrics. Understanding the differences between these two approaches is crucial for effectively analyzing and modeling time series data.








### Interview Questions:

1. Can we solve times series related problem using Linear regression?
2. 


>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
