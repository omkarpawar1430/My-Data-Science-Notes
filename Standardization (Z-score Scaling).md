tags: #stats #ml 

As data scientists we are more interested in "How much different than the Average". 
- Standardization puts all variables on same scales by subtracting the mean ($\bar{x}$) and dividing by standard deviation ($s$).  

$$z = \frac{x - \bar{x}}{s}$$
$x$ - value 
$\bar{x}$ - mean
$s$ - standard deviation
$z$ - Z Score

**$z$ standard deviation away from the mean**

- Standardization insures that scale of original measurement does not effect model. 

### When to use it?

1. **Linear Models**:
    
    - Standardization is commonly used when working with linear models such as linear regression or logistic regression. It ensures that the coefficients of the model represent the change in the dependent variable for a one-standard-deviation change in the independent variable.
2. **PCA (Principal Component Analysis)**:
    
    - Standardization is essential when applying PCA for dimensionality reduction. PCA relies on the covariance matrix of the data, and standardizing features ensures that they have equal influence on the principal components.
3. **Distance-Based Algorithms**:
    
    - Similar to Min-Max scaling, distance-based algorithms like k-nearest neighbors (KNN) or support vector machines (SVM) can benefit from feature standardization. It helps prevent features with larger scales from dominating the distance calculations.
4. **Outlier Handling**:
    
    - Standardization is robust to outliers because it's based on the mean and standard deviation, which are less affected by extreme values. When your data contains outliers, standardization is often a better choice than Min-Max scaling.
5. **Comparing Features**:
    
    - If you want to compare the relative importance of different features in a machine learning model, standardization ensures that features are on the same scale, making it easier to assess their impact.
6. **Interpretable Coefficients**:
    
    - For linear models, the coefficients become more interpretable after standardization because they represent the change in the dependent variable for a one-standard-deviation change in the independent variable.
7. **Rescaling Data**:
    
    - Standardization is commonly used when rescaling data that does not follow a normal distribution. While Min-Max scaling constrains data to a specific range, standardization makes data unitless.
8. **Gradient Descent**:
    
    - Standardized features can improve the convergence speed and stability of gradient-based optimization algorithms like gradient descent. It helps ensure that the steps taken in the optimization process are more consistent across features.
9. **Feature Engineering**:
    
    - When engineering new features or working with data transformations, standardizing can be a helpful step to ensure that the newly created features are on a common scale with the existing ones.
10. **Visualizations**:
    
    - Standardization can be beneficial when creating visualizations that involve multiple features. It makes it easier to compare and visualize the relationships between different variables.