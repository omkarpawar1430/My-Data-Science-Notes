------------------------- 
Tags: #ml 
Date Created:  2023-06-23, @ 11:11

---
>[!info] Keywords
>* hard voting
>* soft voting 
>*  classification
>* ensemble technique 
>* confidence score

Voting in ensemble techniques refers to the process of combining the predictions or decisions from multiple individual models to make a final prediction or decision. It is a common approach in machine learning where multiple models, known as base models or classifiers, are trained independently and then their outputs are aggregated to form the ensemble prediction.

 **Voting is particularly useful when dealing with classification problems and when there is uncertainty or variability in the predictions of individual models**. By combining the outputs of multiple models, voting ensembles can potentially improve the overall prediction accuracy and robustness.

---
### Types of Voting: 
The two main types of voting in ensemble techniques are:

1. [[Hard Voting]]: In hard voting, each individual model in the ensemble makes a prediction, and the final prediction is determined by majority voting. The class that receives the most votes from the individual models is chosen as the ensemble's prediction. Hard voting is effective when the individual models have similar performance and the task is to select the most popular class label.
    
2. [[Soft Voting]]: In soft voting, instead of relying solely on the majority vote, **the individual models in the ensemble provide probabilities or confidence scores for each class label**. The final prediction is then based on the averaged probabilities or scores across the models. This approach takes into account the level of confidence or certainty expressed by each model. Soft voting is beneficial when the individual models have varying degrees of performance and it is desirable to consider the confidence level of each prediction.
    

The choice between hard voting and soft voting depends on the specific problem and the characteristics of the individual models. Hard voting is simpler and appropriate when the models have comparable performance. Soft voting, on the other hand, can be more effective when models have differing capabilities and confidence levels.


---
### Pros of using voting in ensemble techniques:

- Increased prediction accuracy by combining multiple models.
- Robustness to errors from individual models.
- Handling uncertainty and ambiguity in predictions.
- Reduction of overfitting.
- Versatility in incorporating different types of models.

Cons of using voting in ensemble techniques:

- Increased complexity in model training and prediction aggregation.
- Reduced interpretability compared to individual models.
- Potential bias if the ensemble models are similar or biased in the same way.
- Higher computational overhead in terms of time and resources.


>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> [[]]
> []()
