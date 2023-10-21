
------------------------- 
Tags: #ml 
Date Created:  2023-06-07, @ 10:56

---
>[!info] Keywords
>*

![[Support_Vector_Machine.excalidraw|1000]]
### Two Types:
SVM works for both categorical as well as  Continuous Data.

1. [[Support Vector Classifier]]
2. [[Support Vector Regression]]

- SVM works based on [[Logistic Regression]]. 

#### Support Vector Machine: 
Support Vector Machines (SVM) is a popular supervised learning algorithm used for classification and regression tasks. It is particularly effective when dealing with complex datasets with a clear separation between classes or when the data is not linearly separable.

SVM works by creating a decision boundary (hyperplane) that maximally separates different classes in the feature space. It aims to find the best possible hyperplane that maximizes the margin between the classes, which helps in achieving good generalization and robustness to noise.

Here are some key points about SVM:

1. **Linear and Non-linear Classification**: SVM can perform both linear and non-linear classification. In the case of linearly separable data, it finds a linear hyperplane that separates the classes. For non-linearly separable data, SVM uses kernel functions to map the data into a higher-dimensional space where it becomes linearly separable.
    
2. **Margin**: SVM seeks to maximize the margin between the decision boundary and the data points. The margin is the distance between the decision boundary and the nearest data points from each class. By maximizing the margin, SVM aims to achieve better generalization and reduce the risk of misclassification.
    
3. **Support Vectors**: Support vectors are the data points that are closest to the decision boundary. They play a crucial role in defining the decision boundary and are used to make predictions. These support vectors influence the model's learning process and represent the most informative instances in the dataset.
    
4. **Kernel Functions**: Kernel functions are used in SVM to transform the input data into a higher-dimensional feature space. This transformation enables SVM to find non-linear decision boundaries in the original input space. Commonly used kernel functions include the linear kernel, polynomial kernel, and radial basis function (RBF) kernel.
    

When to use SVM and why:

- SVM is effective when dealing with datasets where there is a clear separation between classes or when the data is not linearly separable.
- It is useful in both classification and regression tasks.
- SVM is particularly effective in scenarios with high-dimensional feature spaces.
- It can handle small to medium-sized datasets efficiently.

Concepts related to SVM:

1. **Kernel Trick**: The kernel trick allows SVM to implicitly transform the data into a higher-dimensional feature space without actually calculating the transformed features explicitly. It enables SVM to handle complex, non-linear relationships in the data.
    
2. **Soft Margin SVM**: Soft Margin SVM allows for some misclassifications and violations of the margin in order to handle cases where the data is not perfectly separable. It introduces a penalty parameter that balances the trade-off between maximizing the margin and allowing misclassifications.
    
3. **Multi-class SVM**: SVM is originally designed for binary classification. However, there are techniques such as One-vs-All (OvA) and One-vs-One (OvO) that extend SVM for multi-class classification problems.
    
4. **Hyperparameters**: SVM has hyperparameters that need to be tuned for optimal performance, such as the choice of kernel, kernel parameters, and regularization parameter (C). Proper selection of hyperparameters is essential for achieving good results with SVM.
    
5. **SVM Regression**: SVM can also be used for regression tasks by fitting a hyperplane that minimizes the deviations of the target variable from the predicted values. This is known as Support Vector Regression (SVR).
    

SVM is a versatile algorithm that is widely used in various applications, including text classification, image classification, bioinformatics, and finance, among others. It is chosen when we need a powerful and flexible algorithm that can handle complex data and achieve good generalization.



### Interview Questions:
1. What is the intiution behind the SVM ? explain in layman terms...
	getinng the max marginal distance. 

2. In which case it is ideal to use SVM?
3. 






>[!summary] 
>1. ...
>2. ...

----
>[!cite]
> ![vid](https://youtu.be/H9yACitf-KM)
> [Diagrams](obsidian://open?vault=My%20Data%20Science%20Notes&file=Excalidraw%2FSupport_Vector_Machine.excalidraw)
