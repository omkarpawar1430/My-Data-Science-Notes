------------------------- 
Tags: #ml 
Date Created:  2023-06-24, @ 09:38

---
>[!info] Keywords
>* Adaboost, AdaBoost algorithm, boosting, weak learners, ensemble methods.

- **AdaBoost** (Adaptive Boosting) is a popular machine learning algorithm used for classification tasks.
- It is an ensemble learning method that combines multiple **weak learners** (typically decision trees) to create a strong learner.
- AdaBoost iteratively trains weak models on different subsets of the training data, giving more weight to the samples that were misclassified in the previous iterations.
- This approach allows subsequent weak learners to focus on the difficult instances and improve the overall classification accuracy.
- AdaBoost is useful for dealing with complex datasets or a large number of features.
- It has been successfully applied in various domains, including computer vision, natural language processing, and bioinformatics...


- Advantages of AdaBoost include:
    - Achieving high classification accuracy by combining weak models.
    - Resistance to overfitting due to the iterative nature of the algorithm.
    - Relatively simple implementation with few hyperparameters to tune.


- Limitations of AdaBoost include:
    - Sensitivity to noisy data and outliers, as it assigns higher weights to misclassified instances.
    - Longer training time compared to simpler algorithms since weak learners are trained sequentially.
    - Potential degradation in performance if weak learners are too complex or highly correlated.

### Maths behind it: 

$$pred = h_1(\theta)\alpha_{1} + h_2(\theta)\alpha_{2} + ... + h_n(\theta)\alpha_{n}$$
`alpha` is nothing but the performance of the stomp, where stomp is nothing but decision tree with one node. 

Alpha Value (α): $$α = 0.5 * ln((1 - ε) / ε)$$
The alpha value is calculated based on the weighted error rate (ε) of the decision stump. It determines the contribution of the decision stump in the final ensemble model. The formula is derived from the AdaBoost algorithm's update equations.

The factor `alpha` ensures that model with lower error have a bigger weight. 

>[!summary] 
>1. ...
>2. 

----
>[!cite]
> 
> https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostClassifier.html
