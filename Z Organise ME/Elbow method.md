------------------------- 
Tags: #ml #unsupervised 
⏰ Date Created:  2023-08-10, @ 10:40

-------

![[elbow method.excalidraw | 1000]]

### WCSS 
WCSS stands for "Within-Cluster Sum of Squares." It is a metric used in the K-means clustering algorithm to quantify the variation or dispersion of data points within each cluster. In other words, ==WCSS measures how close the data points are to the center (centroid) of their respective clusters.==

Mathematically, WCSS is calculated as the sum of the squared distances between each data point in a cluster and the centroid of that cluster. Here's the formula for calculating WCSS for a particular cluster 

$$WCSS = \sum (x-u_{i})^2$$


The WCSS value for a specific cluster is essentially the sum of squared distances between all the data points in that cluster and its centroid. Lower WCSS values indicate that the data points are closer to their cluster center, which is a desired outcome of effective clustering.

K-means clustering aims to minimize the overall WCSS across all clusters by iteratively adjusting the cluster assignments and centroids. The lower the total WCSS, the more compact and distinct the clusters are. WCSS is often used as an internal evaluation metric to help determine the optimal number of clusters using techniques like the Elbow Method or the Silhouette Score.

### WCSS 


### Interview Questions:



>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
