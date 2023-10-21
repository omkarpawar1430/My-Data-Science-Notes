------------------------- 
Tags: 
⏰ Date Created:  2023-09-24, @ 10:59

---
>[!info] Keywords
>* 
>* 

Feature scaling is a **data preprocessing technique that focuses on transforming the values of individual features to be within a specific range or follow a specific distribution**. The primary goal of feature scaling is to make sure that the magnitudes of different features do not lead to one feature dominating the others during the learning process.


The choice of feature scaling method depends on the nature of your data and the requirements of the machine learning algorithm you are using. Here's a guide on when to use different feature scaling techniques:

1.  [[Normalisation ( Min Max Scaler )]]:
   - Use when the algorithm you're using requires input features to be within a specific range, typically [0, 1].
   - Suitable for algorithms like neural networks and support vector machines (SVM).
   - Effective when the distribution of your data is approximately uniform.

2.  [[Standardization (Z-score Scaling)]]:
   - Use when your data doesn't follow a normal distribution and when the algorithm doesn't have specific requirements for feature scaling.
   - Suitable for linear regression, logistic regression, k-means clustering, and principal component analysis (PCA).
   - Helps maintain the shape of the distribution and is robust to outliers.

3. **Robust Scaling**:
   - Use when your data contains outliers, as it is less affected by extreme values.
   - Suitable for any algorithm when you suspect the presence of outliers.
   - Transforms data based on the median and interquartile range (IQR).

4. **Max Absolute Scaling**:
   - Use when outliers are not a concern, and you want to preserve the sign of the data.
   - Suitable for algorithms that don't require a specific feature scaling method.
   - Simple and effective for data within a limited range.

5. **Log Transformation**:
   - Use when your data has a highly skewed distribution and you want to make it more symmetric.
   - Suitable for algorithms that assume a more Gaussian-like distribution.

6. **Power Transformation (Box-Cox and Yeo-Johnson)**:
   - Use when you want to stabilize the variance and make the data more Gaussian-like.
   - Suitable for algorithms that require normally distributed data, such as linear regression.

7. **Quantile Transformation**:
   - Use when you want to map your data to a standard Gaussian distribution.
   - Suitable when you want your data to be normally distributed.

8. **Rank Transformation**:
   - Use when the distribution of your data is unknown or irregular.
   - Suitable for any algorithm when you don't have prior information about the data distribution.

9. **Unit Vector Scaling (Vector Normalization)**:
   - Use when you are working with vector-based algorithms like K-Nearest Neighbors (K-NN).
   - Ensures all feature vectors have a Euclidean norm of 1.

In summary, the choice of feature scaling depends on the characteristics of your data and the requirements of the machine learning algorithm. It's often a good practice to experiment with different scaling techniques and evaluate their impact on your model's performance to determine which method is most suitable for your specific task.



### Interview Questions:



>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@datadecides
> 
> https://towardsdatascience.com/what-is-feature-scaling-why-is-it-important-in-machine-learning-2854ae877048
> 
> https://www.analyticsvidhya.com/blog/2020/07/types-of-feature-transformation-and-scaling/



