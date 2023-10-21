------------------------- 
Tags: #ml 
⏰ Date Created:  2023-08-07, @ 20:26

---
>[!info] Keywords
>* Euclidean Distance
>* Manhattan Distance
>* Nearest Neighbors

### Distance Metrics
Similarity (nearness) is determined using a distance metric. 
KNN uses distance metrics like Euclidean Distance and Manhattan Distance to measure the similarity between data points and determine which points are the nearest neighbors. Let's understand how each distance metric works and when to use them:

#### Euclidean Distance 
Euclidean Distance is the most common distance metric used in KNN. It calculates the straight-line distance between two data points in a multi-dimensional feature space. 
For (x_1, x_2, ..., x_p) and (u_1, u_2, ..., u_p)

$$\sqrt{ (x_{1}-u_{1})^{2} + (x_{2}-u_{2})^{2} + \dots + (x_{p}-u_{p})^2 }$$

Euclidean Distance works well when the data has **continuous and numerical features**. It assumes that all dimensions are **equally important and measures the overall similarity between data points**. However, it may not perform optimally when dealing with high-dimensional data or when some features have different scales. In such cases, feature scaling (normalization or standardization) is recommended before applying KNN with Euclidean Distance.

#### Manhattan Distance
Manhattan Distance, also known as City Block Distance or L1 Distance, calculates the distance between two data points by summing the absolute differences along each dimension.
For (x_1, x_2, ..., x_p) and (u_1, u_2, ..., u_p)

$$|x_{1}-u_{1}| + |x_{2}-u_{2}| + \dots + |x_{p}-u_{p}|$$

Manhattan Distance is useful when the data contains discrete or categorical features. Unlike Euclidean Distance, Manhattan Distance is less sensitive to outliers since it only considers the absolute differences. It can work better with data that doesn't follow a smooth distribution or when dealing with high-dimensional data.

When to use which distance:

- Use Euclidean Distance when you have continuous numerical features and want to measure the overall similarity between data points. It's suitable for data that is well-scaled and not too high-dimensional.
- Use Manhattan Distance when you have discrete or categorical features, and you want a distance metric that is less affected by outliers and doesn't assume a smooth distribution of data. It can also be a better choice for high-dimensional data.

### Interview Questions:
1. When to use Manhattan distance and When to use Euclidean distance in KNN? #iq 
2. 


>[!summary] 
>1. Distance Metrics like Euclidean and Manhattan distance are used to find out the Nearest Neighbours.


----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
