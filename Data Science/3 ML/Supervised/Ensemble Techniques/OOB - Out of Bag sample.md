------------------------- 
Tags: #ml
Date Created:  2023-06-17, @ 17:24

---
>[!info] Keywords
>* Out Of Bag
>* cross-validation
>* bootstrapping

When we do bootstrapping and take n number of samples from our data set that we are working on, We can leave some of the data untouched for evaluating model. That left out data samples are called as **Out OF Bag** samples.

The advantage of using the OOB score is that it **provides an unbiased estimate of the model's performance without the need for a separate validation set or performing cross-validation**. It acts as a proxy for the test accuracy and can be useful for model selection, hyperparameter tuning, or comparing different models.

By setting `oob_score=True` when creating a `RandomForestClassifier` instance, scikit-learn automatically calculates the OOB score for you and stores it in the `oob_score_` attribute of the trained model.

>[!summary] 
>1. each tree is trained on a different bootstrap sample, there are data points that were not included in the training of a particular tree. These data points are referred to as out-of-bag (OOB) samples for that specific tree.
>2. ...

----
>[!cite]
> [[]]
> []()
