------------------------- 
Tags: #ml #ensemble_tech #supervised 
Date Created:  2023-06-17, @ 17:04

---
>[!info] Keywords
>*

1. Boosting uses Multiple models sequentially.
2. Boosting requires more care while applying because of `1`

---
### In Layman Terms:

Imagine you're trying to solve a really challenging problem, like predicting whether a given email is spam or not. Boosting is like having a team of experts helping you make the prediction. Each expert is not perfect, but they have their own unique strengths and weaknesses.

Boosting works by training these experts one after another. The first expert looks at the data and tries its best to make predictions. It may make some mistakes, but that's okay because the next expert will focus on correcting those mistakes. The second expert pays more attention to the cases where the first expert struggled and tries to improve upon them. This process continues, with each new expert focusing on the mistakes made by the previous experts.

In the end, you have a team of experts, each specialised in different aspects of the problem, working together to make a final prediction. They learn from each other's mistakes and build upon each other's strengths. This collaborative effort helps them achieve better results than they could individually.

Boosting algorithms, in a similar way, combine these weak models into a strong predictive model that is more accurate and capable of handling complex patterns in the data.

So, boosting is like assembling a team of experts, where each expert learns from the mistakes of others to improve the overall prediction accuracy.

---

In machine learning, boosting is an ensemble technique used to improve the performance of a base learning algorithm by combining multiple weak models into a strong predictive model. Boosting algorithms **iteratively build a series of weak models**, where each subsequent model focuses on correcting the mistakes made by the previous models.

==decision stumps (one-level decision trees)==

There are several types of boosting algorithms, including:

1. [[AdaBoost]] (Adaptive Boosting): It assigns weights to training instances and adjusts them based on the performance of each model iteration. Instances that are misclassified receive higher weights to ensure they are given more attention in subsequent iterations.
    
2. [[Gradient Boosting]]: It builds models in a stage-wise manner, where each new model is trained to correct the mistakes made by the previous models. It uses gradient descent optimization to minimize a loss function.
    
3. [[XGBoost]] (Extreme Gradient Boosting): This is an optimized implementation of gradient boosting that includes additional regularization techniques to control overfitting and handle missing values.
    
4. LightGBM: It is a gradient boosting framework that uses a tree-based learning algorithm. LightGBM is known for its fast and efficient training speed and is often used in large-scale applications.
    
5. [[CatBoost]]: It is another gradient boosting framework that handles categorical features naturally. It incorporates a novel algorithm to deal with categorical variables and provides robust performance.
	
6. [[stochastic boosting]]:  

Boosting algorithms are commonly used when there is a need for high predictive accuracy in machine learning tasks, such as classification and regression. Here are some advantages of using boosting:

1. Improved Accuracy: Boosting combines multiple weak models into a strong model, leading to improved accuracy compared to using a single model.
    
2. Handling Complex Relationships: Boosting algorithms can capture complex patterns and relationships in the data, allowing them to handle difficult learning tasks effectively.
    
3. Reduction of Bias and Variance: Boosting helps reduce both bias and variance in the model, making it less prone to over-fitting or under-fitting.
    
4. Feature Importance: Boosting algorithms can provide insights into the importance of features, helping in feature selection and understanding the underlying data.
    
5. Versatility: Boosting algorithms can be applied to various types of data and can handle both numerical and categorical features.
    

It's important to note that while boosting provides significant benefits, it may also be more computationally expensive and require more training time compared to simpler algorithms. Additionally, **care must be taken to avoid over-fitting, as boosting algorithms can be sensitive to noisy data**.


>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> [[]]
> https://www.geeksforgeeks.org/boosting-in-machine-learning-boosting-and-adaboost/
> 
