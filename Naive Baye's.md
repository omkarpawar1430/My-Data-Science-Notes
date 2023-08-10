------------------------- 
Tags: #ml #classification #regression 
⏰ Date Created:  2023-08-02, @ 15:07

---
>[!info] Keywords
>* Dependent and Independent Events
>* Conditional Probability
>* Bayes Theorem
>* Gaussian Naive Bayes
>* Multinomial Naive Bayes
>* Bernoulli Naive Bayes

The naive Bayes algorithm uses the ==probability of observing predictor values, given an outcome==, to estimate what is really of interest: the probability of observing outcome Y  = i, given set of predictor values.

### Probability 

![[dependent_vs_independent_var.excalidraw | 1000]]

#### Independent Events:
1.  one events outcome don't impact other outcomes

e.g. rolling dice, tossing coin

#### Dependent Events:
1.  one events outcome impact other outcomes

e.g. taking the red or blue marble out of bag

-------
#### Conditional Probability:
Conditional probability is a fundamental concept in probability theory and statistics that allows us to calculate the probability of an event A happening, given that another event B has already occurred. It is denoted as P(A|B) and is read as "the probability of A given B."

-----------
### Mathematical Intuition 

![[Naive_Baye's.excalidraw | 1000]]
We use Bayes theorem which is 
$$Pr(A|B) = \frac{Pr(A)*Pr(B|A)}{Pr(B)}$$
Applying it on our data... $A$ = y and B = $(x_{1}, \dots,x_{n})$
$$Pr\left( \frac{y}{(x_{1},\dots,x_{n})} \right) = \frac{\left( Pr(y)* Pr\left( \frac{x_{1},\dots, x_{n}}{y} \right) \right)}{Pr(x_{1},\dots,x_{n})}$$
$$Pr\left( \frac{y}{(x_{1},\dots,x_{n})} \right) = \frac{Pr(y)*Pr\left( \frac{x_{1}}{y} \right)*\dots*Pr\left( \frac{x_{n}}{y} \right)}{Pr(x_{1})*\dots*Pr(x_{n})}$$
Where
$y$ - is dependent feature
$(x_{1}, \dots, x_{n})$ - are independent features

Outcome with highest probability is declared as prediction

----------
### Variants of Naive Bayes

There are several variants of the Naive Bayes algorithm, each designed to handle different types of data and assumptions.

1. **Gaussian Naive Bayes**: This is the most common variant and is used for continuous data. It assumes that the features follow a Gaussian (normal) distribution within each class. It calculates the mean and standard deviation of each feature for each class and uses them to estimate the likelihood.
    
2. **Multinomial Naive Bayes**: This variant is suitable for discrete data, often used for text classification. It assumes that the features are generated from a multinomial distribution, which is appropriate for count-based data like word frequencies in documents.
    
3. **Bernoulli Naive Bayes**: Another variant for text classification, this assumes that the features are binary (0 or 1). It's often used for situations where you have a bag-of-words representation of text data and want to classify documents based on the presence or absence of specific words.

Numerical data is handled by putting it in buckets. 

-------
### Use Cases:

The Naive Bayes algorithm can be a useful choice under certain circumstances due to its simplicity, speed, and ability to handle high-dimensional data. Here are some situations where you might consider using the Naive Bayes algorithm:

1. **Text Classification**: Naive Bayes is commonly used for text classification tasks, such as spam detection, sentiment analysis, and topic categorization. It works well with bag-of-words or term frequency-inverse document frequency (TF-IDF) representations of text data.
    
2. **Multi-Class Classification**: Naive Bayes can handle multi-class classification problems effectively. If you have a dataset with multiple classes and relatively simple relationships between features and classes, Naive Bayes can provide good results.
    
3. **High-Dimensional Data**: When dealing with datasets that have a high number of features (dimensions), Naive Bayes can still perform well due to its assumption of feature independence. This can be advantageous when other algorithms might struggle with the curse of dimensionality.
    
4. **Quick Initial Baseline**: Naive Bayes is computationally efficient and requires relatively little tuning. It can serve as a quick baseline model to evaluate the performance of more complex algorithms. If Naive Bayes performs well, you might not need to use more computationally intensive methods.
    
5. **Real-Time Applications**: Due to its efficiency, Naive Bayes is suitable for real-time applications where predictions need to be made quickly.
    
6. **Binary and Multi-Class Problems**: Naive Bayes works well for both binary and multi-class classification problems. It's a versatile choice that can handle a variety of scenarios.
    
7. **Simple and Transparent Model**: Naive Bayes is easy to understand and interpret. It provides insights into feature importance and conditional probabilities.
    

However, there are certain situations where Naive Bayes might not be the best choice:

1. **Strong Feature Dependencies**: When features are highly dependent on each other, violating the "naive" independence assumption, Naive Bayes might not perform well.
    
2. **Data with Complex Relationships**: If your data has complex relationships between features and classes, other algorithms like decision trees, random forests, or gradient boosting might provide better results.
    
3. **Continuous Data with Non-Normal Distribution**: While Gaussian Naive Bayes assumes normal distribution for continuous features, if your data doesn't follow this assumption, the model's performance could be compromised.
    
4. **Small Dataset Size**: Naive Bayes tends to perform better with larger datasets. If your dataset is small, the model might not capture the underlying patterns effectively.

#### Dealing with Numerical Data:

1. **Discretization**: Convert continuous numerical features into discrete bins or categories. This can be done by dividing the range of each feature into intervals or bins. Then, you can treat the data as categorical, where each category represents a range of values.
    
2. **Assumption of Gaussian Distribution**: Gaussian Naive Bayes assumes that features follow a Gaussian (normal) distribution within each class. You can estimate the mean and standard deviation of each feature for each class and use these parameters to calculate the likelihoods.
    
3. **Normalization**: Before discretization, you might want to normalize or standardize the numerical features to ensure they have a mean of 0 and standard deviation of 1. This can help the algorithm perform better, as it assumes normal distribution.
    
4. **Discretization Methods**: You can use various methods for discretizing the data, such as equal-width binning, equal-frequency binning, or custom binning based on domain knowledge.
    
5. **Feature Engineering**: If you have insights into the data and believe that certain transformations would improve performance, you can engineer new features that are derived from the original numerical features.
    

>[!warning]
>Keep in mind that discretization introduces an additional level of approximation and might not always work well, especially if the data has a complex distribution. Also, by discretizing, you might lose some fine-grained information present in the original continuous data.

-------------

# Interview Questions:
1. What is the difference between Bernoulli, Multinomial and Gaussian naive Baye's? #iq 
2. When we should use Naive Bayes Algorithm? #iq 
3. 



>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@optimisticomkar
> 
