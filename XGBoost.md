------------------------- 
Tags: #ml #supervised #ensemble_tech #classification #regression 
⏰ Date Created:  2023-08-11, @ 09:34

---
>[!info] Keywords
>* 
>* 



### Rough notes
1. column sampling
2. regularization
3. vast algorithm availble with many lang
4. tree constructions - based on similarity weight also called as cover weight and gain 
5. advanced version of gradeient boosting
6. works with large data set - 2million rows... 
7. 

### **Features of XGBoost:**

1. Can be run on both single and distributed systems(Hadoop, Spark).
2. XGBoost is used in supervised learning(regression and classification problems).
3. Supports parallel processing.
4. Cache optimization.
5. Efficient memory management for large datasets exceeding RAM.
6. Has a variety of regularizations which helps in reducing overfitting.
7. Auto tree pruning – Decision tree will not grow further after certain limits internally.
8. Can handle missing values.
9. Has inbuilt Cross-Validation.
10. Takes care of outliers to some extent.


### **Step-by-Step Explanation of XGBoost:**

1. **Initialization:**
   - Initialize the model with default parameters, which include the number of boosting rounds (iterations) and the learning rate (shrinkage factor).

2. **Compute Initial Predictions:**
   - Make initial predictions using the initialized model. These predictions are usually set to a simple value, like the mean of the target variable.

3. **Compute Residuals:**
   - Calculate the residuals (differences between actual target values and initial predictions).

4. **Build a Weak Learner (Base Model):**
   - Create a weak learner (base model) to predict the residuals. This can be a shallow decision tree with a small number of nodes.

5. **Calculate Weights for Residuals:**
   - Calculate weights for the residuals based on their importance. Larger residuals receive higher weights.

6. **Update Predictions:**
   - Adjust the initial predictions by adding the predictions from the weak learner, multiplied by a small learning rate. This step helps prevent overfitting and controls the contribution of each model.

7. **Repeat for Multiple Rounds:**
   - Iterate steps 3-6 for a specified number of boosting rounds. In each round, you build a new weak learner to predict the weighted residuals from the previous round.

8. **Final Prediction:**
   - Combine the predictions from all weak learners (trees) to get the final prediction. This is done by adding up the predictions while considering the learning rate.

9. **Regularization:**
   - XGBoost includes regularization terms in its objective function to prevent overfitting. These terms penalize complex models, helping to ensure a good balance between bias and variance.

10. **Pruning and Tree Growth:**
    - XGBoost employs a depth-first tree growth strategy with pruning. It explores the best splits and prunes trees' branches if they don't contribute positively to the objective.

11. **Feature Importance:**
    - XGBoost provides a way to calculate feature importance based on how often features are used in the tree ensemble and how much they contribute to reducing the loss function.

12. **Weighted Quantile Sketch:**
    - XGBoost uses a data structure called "weighted quantile sketch" to efficiently find the best split points during tree construction. This helps speed up the algorithm significantly.


### Interview Questions:

1. How does XGBoost differ from traditional gradient boosting?
2. Explain the concept of weighted quantile sketch and its role in XGBoost.
3. What is the significance of the learning rate in XGBoost?
4. How does XGBoost handle overfitting?
5. Can you explain the regularization terms used in XGBoost's objective function?
6. How is feature importance calculated in XGBoost?
7. What is pruning, and how does XGBoost use it during tree growth?

>[!summary] 
>XGBoost is an advanced gradient boosting algorithm that enhances the traditional gradient boosting process with techniques like regularization, weighted quantile sketch, and efficient tree construction. It iteratively builds a series of weak learners, each focusing on correcting the errors of the previous rounds. The final prediction is a combination of the predictions from all the weak learners. XGBoost's ability to handle complex relationships, efficient computation, and feature importance analysis makes it a popular choice in various machine learning competitions and real-world applications.

----
>[!cite]
>https://analyticsindiamag.com/xgboost-internal-working-to-make-decision-trees-and-deduce-predictions/
>https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html
>https://www.kdnuggets.com/2018/08/unveiling-mathematics-behind-xgboost.html
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
