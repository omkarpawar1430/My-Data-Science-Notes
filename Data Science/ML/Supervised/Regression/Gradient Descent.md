
Tags: #stats #ml 

------------------------------------------
Gradient descent is an iterative optimization algorithm that is commonly used to find the parameters that minimize the cost or loss function in machine learning models such as simple linear regression. The basic idea behind gradient descent is to iteratively adjust the parameters in the direction of the steepest descent of the cost function until **convergence** is achieved.

The gradient descent algorithm starts with an initial estimate of the slope and intercept of the regression line, and then updates these estimates iteratively based on the **gradient of the cost function with respect to the parameters**. The gradient represents the direction of steepest ascent of the cost function, so by taking the negative of the gradient, we can move in the direction of steepest descent and find the minimum of the cost function.

In each iteration of the gradient descent algorithm, the parameters are updated as follows:

`new_parameter = old_parameter - learning_rate * gradient
`
where the **learning rate is a hyperparameter that controls the step size of the update**. The learning rate must be chosen carefully to ensure convergence and avoid overshooting or oscillations.

The convergence algorithm is used to determine when to stop the iterative process and declare that the algorithm has converged to a solution. Without a convergence algorithm, the gradient descent algorithm would continue to update the parameters indefinitely, which could result in overfitting or other issues.

----
------------------------- 

### Topic: Gradient Descent
Tags: #ml 
Date Created:  2023-05-13, @ 14:21

---

<aside>
🧠 Recall
</aside>
- Convergence Algorithm 
- Parameters
- Optimisation Algorithms

<aside>
📄 Notes

</aside>
- Gradient Descent is an iterative algorithm used to find the best fit line. And [[Convergence Algorithm]] is the algorithm is the one which stops algorithm when convergence (best fit line) is achieved.
- gradient descent can be slow to converge, especially for large datasets as it's iterative. It is easy to apply but heavy on computation.
- 
![image](data:image/png;base64,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)

*  


---

<aside>
📌 SUMMARY:

</aside>


---

#### Links:
	[[]]
---------------------
#### links:
[[]]
[[]]