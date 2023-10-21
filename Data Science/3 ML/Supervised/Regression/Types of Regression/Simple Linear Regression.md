
Tags: #ml 

------------------------------------------
### What is simple linear regression?

Simple linear regression is a statistical method that uses a straight line to model the relationship between one independent variable (x) and one dependent variable (y). The line is called the [[regression line]] ( Best fit line ) , and it is used to predict the value of y for a given value of x.
         
#### Example:
For example, you could use simple linear regression to model the relationship between the number of hours you study and your exam score. You would collect data on the number of hours you study and your exam scores, and then use a statistical software to fit a regression line to the data. The regression line would allow you to predict your exam score for a given number of hours of studying.

![Diagram](https://editor.analyticsvidhya.com/uploads/375512.jpg)
![diagram](https://miro.medium.com/v2/resize:fit:960/1*jt-pyQQ7bgL2lyganse0nQ.png)

---

### Aim:

To create a **best fit line** where error (squared residual) is minimal. and that point is called [[Global Minimum]]. 

**squared residual**/Squared Error: vertical distance between the point of the data set and the fitted line

* **The smaller the sum of the squared errors, the better the line fits the data.**

There are two parameters that are used to define the regression line: the slope and the intercept. The slope of the line is the change in y for a one-unit change in x. The intercept is the value of y when x is zero.

**Residual** for a point in the data is the difference between the actual value and the value predicted by our linear regression model. (loss function, cost functions)

![img](https://cdn.analyticsvidhya.com/wp-content/uploads/2020/07/residual.png)

##### IMP:
-   **Residual** is the difference between the predicted value of a dependent variable and the actual value of a dependent variable.
-   **Loss function** is a function that measures the error between the predicted values of a dependent variable and the actual values of a dependent variable.
-   **Cost function** is a loss function that is averaged over all of the data points in a dataset.

In other words, a residual is a single error, a loss function is a way of measuring the total error in a model, and a cost function is a way of measuring the total error in a model averaged over all of the data points.

---
### Methods to Get Best Fit Line:
* [[Gradient Descent]]

**How to interpret the results of simple linear regression**

The results of simple linear regression can be interpreted in a number of ways. One way to interpret the results is to look at the slope of the line. The slope of the line tells you how much y changes for a one-unit change in x. For example, if the slope of the line is 2, then for every one-hour increase in studying, your exam score will increase by 2 points.

Another way to interpret the results is to look at the intercept of the line. The intercept of the line tells you the value of y when x is zero. For example, if the intercept of the line is 50, then your exam score would be 50 if you did not study at all.

**When to use simple linear regression**

Simple linear regression can be used to model the relationship between two variables when the following conditions are met:

-   The relationship between the two variables is linear. This means that the change in y is proportional to the change in x.
-   The data is normally distributed. This means that the data is spread evenly around the regression line.
-   The data is independent. This means that the value of one data point does not affect the value of another data point.

**Advantages and disadvantages of simple linear regression**

Simple linear regression is a powerful tool that can be used to model the relationship between two variables. However, it is important to be aware of the advantages and disadvantages of simple linear regression before using it.

**Advantages of simple linear regression:**

-   Simple linear regression is relatively easy to understand and use.
-   Simple linear regression can be used to model a wide variety of relationships between two variables.
-   Simple linear regression is a relatively efficient way to model the relationship between two variables.

**Disadvantages of simple linear regression:**

-   Simple linear regression can only be used to model linear relationships between two variables.
-   Simple linear regression is **sensitive to outliers**.
-   Simple linear regression can only be used to make predictions within the range of the data that was used to fit the model.

---------------------
#### links:
[[Cost Functions]]
[[]]