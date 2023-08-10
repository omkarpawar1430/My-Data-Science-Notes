------------------------- 
Tags: #ml #classification #regression #supervised 
⏰ Date Created:  2023-08-04, @ 09:47

---
>[!info] Keywords
>* K
>* Neighbour
>* Distance Metrics

>1. Neighbour - A record that has similar predicted values to another records
>2. Distance Metrics - Measures that sum up in a single number how far one record is from another record
>3. K - The number of neighbours  considered in the nearest neighbour calculation

-----------
### Step by Step Implementation

Step 1: Gather the Data The first step in KNN is to gather the dataset. This dataset should contain the information you want to use for classification or regression. Each data point in the dataset should be represented by a set of features and a corresponding label (in the case of classification) or target value (in the case of regression).

Step 2: Choose the Value of 'k' The second step is to choose the value of 'k' in KNN. 'k' represents the number of nearest neighbours that will be considered when making a prediction. It's an essential hyperparameter in the KNN algorithm, and its value can impact the performance of the model. A small 'k' might lead to noisy predictions, while a large 'k' may oversmooth the decision boundaries.

Step 3: Calculate the Distance For each data point in the dataset, the next step is to calculate the distance between that data point and all other data points in the dataset. The distance is typically computed using a [[Distance Metrics]] like Euclidean Distance or Manhattan Distance, as discussed earlier. This distance metric measures how similar or dissimilar the data points are in the feature space.

- Hyper parameter tuning is used to decide which distance metrics should be used

- For continuous data we calculate the average of the distance.  

Step 4: Identify the 'k' Nearest Neighbours After calculating the distances, the algorithm identifies the 'k' data points that are closest to the data point for which we want to make a prediction. These 'k' data points are called the nearest neighbours.

![[KNN.excalidraw | 10000]]

- This is computationally heavy method for larger data sets

Step 5: Count the Labels (for Classification) or Average the Target Values (for Regression) In the case of classification, the algorithm counts the occurrences of each class among the 'k' nearest neighbours. The class with the highest count becomes the predicted class for the data point.


For regression, the algorithm takes the average of the target values of the 'k' nearest neighbours. This average value becomes the predicted target value for the data point.

Step 6: Make the Prediction With the information from the previous step, the algorithm makes the final prediction for the data point. If it's a classification problem, the predicted class is the one with the highest count among the 'k' nearest neighbours. If it's a regression problem, the predicted target value is the average of the target values of the 'k' nearest neighbours.

Step 7: Repeat for All Data Points The previous steps are repeated for each data point in the dataset, and predictions are made for all of them.

Step 8: Evaluate the Model Once the predictions are made, the performance of the KNN model is evaluated using appropriate evaluation metrics like accuracy (for classification) or mean squared error (for regression). The model's performance is analyzed to understand how well it's doing in predicting the outcomes.

Step 9: Use the Model for New Data Once the model is trained and evaluated, it can be used to make predictions for new, unseen data points. The algorithm calculates the distances from the new data point to all other data points in the training set, identifies the 'k' nearest neighbors, and uses the majority class (for classification) or the average target value (for regression) to predict the outcome for the new data point.

----------
### Variants of KNN
#### K Dimension Tree

![[K Dimension Tree.excalidraw | 10000]]
- It reduces the computational efforts needed while using simple KNN
- All the data points gets split and we create a decision tree. 
- When we have new point then it looks for smallest nearest point then it traverse through decision tree to find other nearest points. 
- This way our model don't have to go to each and every data points which reduces computational power needed. 
#### Step by step explanation:

1. **Choose a Root Node:**
    
    - Start with the entire dataset as your root node. This represents all the data points you want to organize and search within.
2. **Split the Data:**
    
    - Select a dimension (attribute) to split the data. This choice could be based on various factors, like evenly distributing points or focusing on the most varying dimension.
    - Divide the data into two subsets along this dimension. For example, in a 2D space, you might split vertically based on the x-coordinate.
3. **Create Child Nodes:**
    
    - For each of the subsets created, designate child nodes. These child nodes become new root nodes for their respective subsets.
4. **Repeat:**
    
    - Continue the process recursively for each child node.
    - Choose a different dimension for splitting this time. If you split vertically in the parent node, split horizontally for the child nodes, and vice versa.
    - Divide the data again into two subsets and create child nodes for each subset.
5. **Stop Conditions:**
    
    - Define stopping conditions for splitting. This could involve criteria such as a maximum tree depth, a minimum number of points in a node, or other factors that prevent excessive splitting.
6. **Search:**
    
    - To search for the nearest neighbors of a query point, start at the root node.
    - Compare the query point's value in the current splitting dimension to the value in the node.
    - If it's smaller, move to the left child node; if it's larger, move to the right child node. This narrows down the search space based on the query's location.
7. **Backtrack:**
    
    - As you traverse down the tree, keep track of the nodes you visit.
    - Whenever you reach a node, calculate the distance between the query point and the node's point.
    - If this distance is smaller than the distance to any previously encountered nearest neighbors, update your list of nearest neighbors.
8. **Optimization:**
    
    - Implement techniques like pruning, which involves skipping entire subtrees when you determine that they can't contain points closer than your current nearest neighbors.
    - Also, consider early termination if you've found enough nearest neighbors based on their distances.
9. **K-Nearest Neighbors:**
    
    - For k-nearest neighbors, you're not just looking for the closest point but the k closest points.
    - Modify the search process to keep track of the top k nearest points as you traverse the tree.
10. **Distance Calculation:**
    
- Calculate the distance between the query point and the points in the nodes you visit.
- Update the k-nearest points if you find points that are closer than the farthest point in the current list.

11. **Return Results:**

- Once the search is complete, return the k-nearest points along with their distances.
- These points are the neighbors that are closest to the query point in the multi-dimensional space.

In essence, a K-D Tree is like a multi-dimensional binary search tree optimized for efficient nearest neighbor searches. **It allows you to organize and navigate through data points in a way that reduces the number of comparisons needed to find the nearest neighbors, making it a powerful tool for spatial data searching and retrieval.**

----------
### **Ball Tree** 
A Ball Tree organizes data points in nested hyperspheres (balls). Each node of the tree represents a hypersphere that encloses its child nodes' hyperspheres. The hyperspheres are created in such a way that they cover the data points efficiently. The Ball Tree is designed to address the limitations of the K-D Tree in high-dimensional spaces by focusing on the relationship between distances and hyperspheres.

-------
#### **Key Differences and When to Use:**

- **Dimensionality:** K-D Trees perform well in lower-dimensional spaces (up to around 20 dimensions), whereas Ball Trees are designed to handle [[higher-dimensional space]]s more efficiently.
- **Search Efficiency:** Ball Trees generally handle the curse of dimensionality better due to their use of hyperspheres. They can be more efficient than K-D Trees in high-dimensional spaces.
- **Construction Complexity:** Constructing a Ball Tree can be more complex than building a K-D Tree, especially due to the need to determine the radius of hyperspheres.
- **Data Distribution:** K-D Trees can work well when data points are not uniformly distributed, but Ball Trees can perform better in cases where data points are more uniformly distributed within their hyperspheres.
- **Trade-offs:** K-D Trees might be a better choice for lower-dimensional data or when you're interested in axes-aligned splits. Ball Trees are more suited for high-dimensional data with complex distance relationships.

#### **When to Use Which:**

- Use **K-D Trees** when dealing with:
    - Lower-dimensional spaces (up to around 20 dimensions).
    - Data with axes-aligned features.
    - Data with non-uniform distributions.
- Use **Ball Trees** when dealing with:
    - High-dimensional spaces (beyond 20 dimensions).
    - Data with more uniform distributions.
    - Cases where K-D Trees' performance degrades due to the curse of dimensionality.
---------
### Choosing K 
- if K is too low : overfitting
- if K is  too high : oversmooth , which losses ability to capture local structure in the data. 
- For highly structured data with little noise, small values of K works best

What is the term [[Signal-to-Noise-Ration (SNR)]]? #iq 

- Typically value of K falls in the range of 1 to 20 and often an odd number is chosen. 



### Interview Questions:






>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> https://varshasaini.in/kd-tree-and-ball-tree-knn-algorithm/


