------------------------- 
Tags: #ml 
Date Created:  2023-06-04, @ 10:57

---
>[!info] Keywords
>*

In machine learning, a **hyperparameter** is a parameter whose value is set before the learning process begins. By contrast, the values of other parameters (typically node weights) are derived via training. Hyperparameters can be classified as model hyperparameters, that cannot be inferred while fitting the machine to the training set because they refer to the model selection task, or algorithm hyperparameters, that in principle have no influence on the performance of the model but affect the speed and quality of the learning process. An example of a model hyperparameter is the topology and size of a neural network.

Examples of algorithm hyperparameters are learning rate and batch size as well as mini-batch size. Batch size can refer to the full data sample where mini-batch size would be a smaller sample set. Different model training algorithms require different hyperparameters, some simple algorithms (such as ordinary least squares regression) require none. Given these hyperparameters, the training algorithm learns the parameters from the data. For instance, LASSO is an algorithm that adds a regularization hyperparameter to ordinary least squares regression, which has to be set before estimating the parameters through the training algorithm.

Here are some examples of hyperparameters:

- Learning rate: This is the rate at which the model learns from the data. A higher learning rate will cause the model to learn more quickly, but it may also cause the model to overfit the data.
- Number of epochs: This is the number of times the model will be trained on the data. A higher number of epochs will cause the model to learn more from the data, but it will also take longer to train the model.
- Batch size: This is the number of data points that will be used to train the model at a time. A larger batch size will cause the model to learn more efficiently, but it will also require more memory.
- Regularization: This is a technique that is used to prevent the model from overfitting the data. There are many different types of regularization, and the best type to use will depend on the data and the model.

Hyperparameter tuning is the process of finding the best values for the hyperparameters. This can be a time-consuming process, but it is important to tune the hyperparameters in order to get the best performance from the model. There are many different techniques that can be used for hyperparameter tuning, and the best technique to use will depend on the data and the model.

Here are some techniques for hyperparameter tuning:

- Grid search: This is a brute-force method that tries all possible combinations of hyperparameter values. This can be very time-consuming, but it is guaranteed to find the best hyperparameter values.
- Random search: This is a more efficient method than grid search. It randomly selects hyperparameter values from a pre-defined range. This can be less accurate than grid search, but it is much faster.
- Bayesian optimization: This is a more sophisticated method than grid search or random search. It uses a Bayesian model to estimate the best hyperparameter values. This can be more accurate than grid search or random search, but it is also more computationally expensive.

Hyperparameter tuning is an important part of machine learning. By tuning the hyperparameters, you can get the best performance from your model.


>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> [[]]
> []()
