
Tags: #ml 

------------------------------------------
To solve classification problems: 
	1. Binary Classification 
	2. Multi class Classification

			Sigmoid function is used to keep the Regression lines output within certain range by bending the best fit line at certain points. It will help to deal with outliers

![image](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cb/Exam_pass_logistic_curve.svg/600px-Exam_pass_logistic_curve.svg.png)

* Logistic Regression is also a supervised learning algorithm, but it is used for **binary classification tasks**.
-----------
Logistic regression is a widely used statistical and machine learning algorithm for [[binary classification]] problems. It is named after the logistic function, also known as the [[sigmoid function]], which is a key component of the algorithm. Logistic regression is a supervised learning algorithm that can predict the probability of an instance belonging to a certain class.

Here are the key aspects and steps involved in logistic regression:

1. Assumptions:
    
    - Binary outcome: Logistic regression is suitable for problems where the target variable has two possible outcomes, typically represented as 0 and 1.
    - Linearity: The relationship between the features and the log-odds of the target variable is assumed to be linear.
    - Independence of errors: The observations are assumed to be independent of each other.
    - 
2. Model Representation:
    
    - The logistic regression model represents the relationship between the features (independent variables) and the probability of the target variable (dependent variable) being in a certain class.
    - The logistic function (sigmoid function) is used to transform the linear combination of the features into a value between 0 and 1, which represents the predicted probability.
3. Model Training:
    
    - The logistic regression model is trained using a process called maximum likelihood estimation.
    - The objective is to find the set of model parameters that maximizes the likelihood of the observed data.
    - This is typically achieved by minimizing a cost function, such as the negative log-likelihood or cross-entropy loss, using optimization techniques like gradient descent.
4. Feature Scaling:
    
    - Before fitting the logistic regression model, it is often beneficial to scale the features to a similar range to prevent any particular feature from dominating the others.
    - Common scaling methods include standardization (subtracting mean and dividing by standard deviation) or normalization (scaling values to the range [0, 1]).
5. Decision Boundary and Prediction:
    
    - Once the logistic regression model is trained, it can be used to make predictions on new instances.
    - A decision boundary is set to classify instances based on their predicted probabilities. The decision boundary is typically set at a threshold of 0.5 (probability above 0.5 belongs to one class, and below 0.5 belongs to the other class).
    - Predictions can be made by evaluating the logistic function with the new instance's feature values and comparing the output to the decision boundary.
6. Evaluation Metrics:
    
    - Various evaluation metrics can be used to assess the performance of a logistic regression model, including accuracy, precision, recall, F1 score, and area under the ROC curve (AUC-ROC).
    - These metrics provide insights into how well the model is predicting the positive and negative classes and the trade-offs between different performance aspects.

Logistic regression is a powerful and interpretable algorithm that can handle both numerical and categorical features. While it is primarily used for binary classification, it can be extended to handle multi-class classification problems through techniques like one-vs-rest or softmax regression.











---------------------
#### links:
[[Multi class Logistic Regression]] 
[[]]