------------------------- 
Tags: #ml 
Date Created:  2023-06-24, @ 09:38

---
>[!info] Keywords
> * Stomp 
>*  Adaboost, AdaBoost algorithm, boosting, weak learners, ensemble methods.

- **AdaBoost** (Adaptive Boosting) is a popular machine learning algorithm used for classification tasks.
- It is an ensemble learning method that combines multiple **weak learners** (typically decision trees) to create a strong learner.
- **Depth of the decision tree is 1**
- AdaBoost iteratively trains weak models on different subsets of the training data, giving more weight to the samples that were misclassified in the previous iterations.
- This approach allows subsequent weak learners to focus on the difficult instances and improve the overall classification accuracy.
- AdaBoost is useful for dealing with complex datasets or a large number of features.
- It has been successfully applied in various domains, including computer vision, natural language processing, and bioinformatics...
-------
### When to Use: 
It is particularly useful in situations where you have a ==binary classification problem== and want to improve the performance of your model. Here are a few situations where you might consider using AdaBoost:

1. **Imbalanced datasets**: When you have imbalanced data with a significant difference in the number of instances between the two classes, AdaBoost can be effective. It helps in giving more weight to the minority class during training, allowing the model to focus on difficult-to-classify instances and improve overall classification accuracy.
    
2. **Weak classifiers**: AdaBoost works well with weak classifiers, also known as base learners, that perform only slightly better than random guessing. It sequentially trains these weak classifiers by adjusting the weights of the training instances, emphasizing the misclassified ones. The ensemble of these weak classifiers, weighted by their performance, forms a strong classifier.
    
3. **Feature selection**: **AdaBoost can serve as a feature selection technique**. __By observing the weights assigned to the features during training, you can identify which features contribute the most to improving the model's performance.__ This information can be valuable for understanding the importance of different features and potentially reducing dimensionality.
    
4. **Noisy data**: When your dataset contains noisy or mislabeled instances, AdaBoost can handle them effectively. As the algorithm focuses more on misclassified instances during training, it can adapt to the noisy data points and reduce their impact on the final model.
    
5. **Real-world applications**: AdaBoost has been successfully applied to a wide range of real-world applications, such as face detection, object recognition, and text categorization. It can handle complex decision boundaries and capture intricate patterns in the data, making it suitable for various domains.
--------
### Advantages of AdaBoost include:
 - Achieving high classification accuracy by combining weak models.
- Resistance to overfitting due to the iterative nature of the algorithm.
- Relatively simple implementation with few hyperparameters to tune.


### Limitations of AdaBoost include:
- Sensitivity to noisy data and outliers, as it assigns higher weights to misclassified instances.
- Longer training time compared to simpler algorithms since weak learners are trained sequentially.
- Potential degradation in performance if weak learners are too complex or highly correlated.
--------
### Maths behind it: 

$$pred = h_1(\theta)\alpha_{1} + h_2(\theta)\alpha_{2} + ... + h_n(\theta)\alpha_{n}$$
`alpha` is nothing but the performance of the stomp, **stomp** is decision tree with depth one. 

**`alpha` value will be different for each and every stomp. 
That means some stomps get more say than other stomps.** 

Alpha Value (α): Performance/Weight of the stomp:
$$α = 0.5 * ln((1 - ε) / ε)$$
The alpha value is calculated based on the weighted error rate (ε) of the decision stump. It determines the contribution of the decision stump in the final ensemble model. The formula is derived from the AdaBoost algorithm's update equations.

The factor `alpha` ensures that model with lower error have a bigger weight. 

>[!summary] 
>1. Adaboost is used for Binary Classification Mostly. 
>2. It is made up of bunch of weak learners (stomps i.e. Decision Tree with Depth one) to collectively form a strong learner. 
>3. `alpha` value is performance of stomp, every stomp gets different weight so there contribution in decision making is different. 


----
>[!cite] 
>
> https://www.analyticsvidhya.com/blog/2021/09/adaboost-algorithm-a-complete-guide-for-beginners/
> 
> [SkLearn](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostClassifier.html)
