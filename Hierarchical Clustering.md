------------------------- 
Tags: #ml #unsupervised 
⏰ Date Created:  2023-08-10, @ 14:18

---
>[!info] Keywords
>* 
>* 

Hierarchical clustering is an unsupervised machine learning technique used to group similar data points into clusters in a hierarchical way. It builds a tree-like structure of clusters, known as a dendrogram, which shows how data points are grouped at different levels of similarity. Here's a step-by-step explanation of hierarchical clustering in simple terms:

### Step by step Implementation  
**Step 1: Start with Individual Data Points**

- Begin with each data point as its own cluster. This means each data point is a separate cluster at the beginning.

**Step 2: Measure Pairwise Similarities**

- Calculate the similarity (or distance) between each pair of data points. Common similarity measures include Euclidean distance or cosine similarity.

**Step 3: Merge Closest Data Points or Clusters**

- Identify the two closest data points or clusters based on their similarity.
- Merge these two data points or clusters into a single cluster. This creates a new cluster that contains the merged data points.

**Step 4: Update Similarity Matrix**

- Recalculate the similarity between the new cluster and all other data points or clusters. This involves updating the similarity matrix.

**Step 5: Repeat Merging and Updating**

- Repeat steps 3 and 4 iteratively. This involves finding the next closest pair of data points or clusters, merging them, and updating the similarity matrix.

![[Hierarchical Clustering.excalidraw | 1000]]

**Step 6: Build the Dendrogram**

- As you repeat the merging and updating steps, you create a hierarchy of clusters. This hierarchy is represented by a dendrogram, which is a tree-like structure showing how clusters are linked at different levels of similarity.

**Step 7: Choose Number of Clusters**

- Decide how many clusters you want to end up with. You can cut the dendrogram at a certain level to determine the number of clusters.

**Step 8: Assign Data Points to Clusters**

- Depending on the number of clusters you chose in the previous step, cut the dendrogram at the appropriate level.
- Each final branch or cluster in the dendrogram becomes a cluster, and data points are assigned to these clusters.

**Step 9: Interpret the Clusters**

- Analyze the clusters to understand the patterns and relationships in your data.
- Data points within the same cluster are more similar to each other compared to those in different clusters.

**Advantages:**

- Hierarchical clustering provides a visual representation of how data points are grouped.
- It doesn't require specifying the number of clusters beforehand.

**Disadvantages:**

- It can be computationally expensive for large datasets.
- The choice of linkage method (how distances are measured between clusters) can impact the results.

In summary, hierarchical clustering builds a hierarchy of clusters by iteratively merging similar data points or clusters. It creates a dendrogram that helps you decide how to group your data into clusters based on the desired level of similarity.

Because dendrogram becomes complicated we can't use it for huge data sets. 

-----------
### Types of Hierarchical clustering:

Hierarchical clustering can be divided into two main types: agglomerative and divisive.

1. **Agglomerative Hierarchical Clustering:**
    
    - Agglomerative clustering starts with each data point as its own cluster.
    - It iteratively merges the closest clusters based on a chosen similarity measure (e.g., Euclidean distance).
    - As the process continues, clusters are progressively combined into larger clusters.
    - The algorithm stops when all data points belong to a single cluster, forming a dendrogram that shows how clusters are linked at different levels of similarity.
    - Agglomerative clustering is like "bottom-up" clustering, where you start from the bottom (individual data points) and merge upwards.
2. **Divisive Hierarchical Clustering:**
    
    - Divisive clustering starts with all data points in a single cluster.
    - It iteratively divides the existing clusters into smaller clusters.
    - At each step, the cluster that's most dissimilar or least cohesive is split into two smaller clusters.
    - This process continues until each data point forms its own cluster, resulting in a dendrogram.
    - Divisive clustering is like "top-down" clustering, where you start from the top (all data points) and divide downwards.

Both agglomerative and divisive hierarchical clustering methods have their own advantages and disadvantages. Agglomerative clustering tends to be more common and widely used because it's computationally more efficient and often produces satisfactory results. Divisive clustering can be more complex and computationally intensive, making it less commonly used in practice.

-------
### Interview Questions:

1. **Explain the concept of hierarchical clustering in unsupervised machine learning. How does it differ from other clustering algorithms?** #iq 
    
    - Hierarchical clustering is a method that groups similar data points into clusters in a hierarchical manner, creating a tree-like structure called a dendrogram. It differs from other clustering algorithms by building a step-by-step hierarchy of clusters rather than directly assigning data points to specific clusters like K-means.
2. **What is a dendrogram in the context of hierarchical clustering? How does it visually represent the clustering process?** #iq 
    
    - A dendrogram is a graphical representation of hierarchical clustering. It shows how data points or clusters are linked at different levels of similarity. The vertical lines represent clusters, and the height at which they merge indicates their similarity. The longer the line, the less similar the clusters are.
3. **Describe the main steps involved in agglomerative hierarchical clustering. How does it build clusters from individual data points?**
    
    - Agglomerative hierarchical clustering starts with each data point as a separate cluster.
    - It calculates pairwise distances/similarities between data points.
    - It merges the closest clusters iteratively based on a chosen linkage method.
    - The process continues until all data points belong to a single cluster, creating a dendrogram.
4. **Contrast agglomerative and divisive hierarchical clustering. How do they start and proceed differently in creating clusters?**
    
    - Agglomerative starts with individual data points and merges them, while divisive starts with all data points in one cluster and divides it.
    - Agglomerative builds clusters from the bottom up, and divisive divides clusters from the top down.
5. **What are some common similarity measures used in hierarchical clustering to calculate distances between data points or clusters?**
    
    - Common similarity measures include Euclidean distance, Manhattan distance, cosine similarity, and correlation coefficient.
6. **How does the choice of linkage method (single, complete, average, etc.) impact the results of hierarchical clustering?**
    
    - Linkage method determines how the distance/similarity between clusters is calculated.
    - Single linkage is sensitive to outliers, complete linkage is robust to outliers, and average linkage balances both.
7. **What is the advantage of not needing to specify the number of clusters beforehand in hierarchical clustering? How do you determine the number of clusters post-clustering?**
    
    - The advantage is flexibility, as you don't need to predefine the number of clusters.
    - You determine the number of clusters by analyzing the dendrogram and finding a suitable level to cut it.
8. **Explain how the agglomerative hierarchical clustering algorithm decides which clusters to merge at each step.**
    
    - It merges the closest clusters based on the linkage method's distance/similarity criterion.
9. **Why might divisive hierarchical clustering be less commonly used compared to agglomerative clustering? What are some challenges associated with divisive clustering?**
    
    - Divisive clustering is more complex and computationally intensive.
    - It's harder to decide which cluster to split at each step.
10. **Discuss the computational complexity of hierarchical clustering. How does it scale with the size of the dataset?**
    
    - Agglomerative clustering has a time complexity of about O(n^2 log n) to O(n^3), where n is the number of data points.
    - It scales poorly for large datasets due to the pairwise distance calculations.
11. **How can you interpret the results of hierarchical clustering? How might you analyze the dendrogram to make decisions about the number of clusters?**
    
    - You can interpret clusters based on their proximity in the dendrogram.
    - The height at which you cut the dendrogram determines the number of clusters.
12. **Can hierarchical clustering handle datasets with varying cluster densities and shapes effectively? Why or why not?**
    
    - Hierarchical clustering can handle varying cluster densities and shapes to some extent.
    - However, it might struggle with irregularly shaped or noisy clusters.
13. **Describe a scenario where hierarchical clustering might be particularly useful in real-world applications.**
    
    - It could be useful for classifying species based on genetic features, where the hierarchy might represent taxonomic relationships.
14. **What are some limitations of hierarchical clustering? How might its performance be impacted by noisy or outlier data points?**
    
    - Hierarchical clustering might not perform well on very large datasets due to computational complexity.
    - Noisy or outlier data points can disrupt the formation of meaningful clusters.
15. **Compare hierarchical clustering with other clustering algorithms, such as K-means or DBSCAN. What are the strengths and weaknesses of each approach?**
    
    - Hierarchical clustering doesn't require specifying the number of clusters and produces a dendrogram.
    - K-means is efficient but requires pre-defining the number of clusters.
    - DBSCAN is good at handling noise and irregularly shaped clusters but might struggle with varying densities.

>[!summary] 
>Hierarchical clustering groups similar data points into clusters hierarchically. Agglomerative clustering starts with individual data points and merges them, while divisive clustering begins with all data points in one cluster and divides them. Agglomerative creates a dendrogram showing clustering relationships. Linkage methods (single, complete, average) impact results. The advantage is not needing to predefine clusters. Interpretation and determining clusters involve analyzing the dendrogram. Hierarchical clustering handles varying shapes but struggles with large datasets and noise. Comparison with K-means and DBSCAN reveals strengths and weaknesses of each.

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
