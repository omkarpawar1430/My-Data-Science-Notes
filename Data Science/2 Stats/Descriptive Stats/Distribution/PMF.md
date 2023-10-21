
Tags: #stats 

------------------------------------------

- A probability mass function (PMF) gives the probability that a discrete random variable is exactly equal to some value. ( 0, 1)
- A PMF can be seen as a special case of a distribution or a density function with respect to the counting measure.
- A PMF must be non-negative and sum up to 1 for all possible values of the random variable.
- Examples of PMFs include the Bernoulli distribution and the binomial distribution.
- A PMF is different from a probability density function (PDF), which is for continuous random variables and requires integration to get probabilities.
- Cumulative Distribution function:
    
    The **cumulative distribution function (CDF)** is a function that maps each possible value of a random variable to the probability that the random variable takes a value less than or equal to that value
    
    
    
    The cumulative distribution function (CDF) of a discrete random variable X is defined as F(x) = P(X ≤ x). It can be computed by summing these probabilities sequentially. For example, if X is a discrete random variable with possible values 1, 2, 3, 4, 5, and 6 and corresponding probabilities 1/6, 1/6, 1/6, 1/6, 1/6, and 1/6 respectively, then the CDF can be computed as follows:
    ![[Pasted image 20230505202734.png]]
    
    - Pr(X ≤ 1) = 1/6
    - Pr(X ≤ 2) = Pr(X ≤ 1) + Pr(X = 2) = (1/6) + (1/6) = 2/6
    - Pr(X ≤ 3) = Pr(X ≤ 2) + Pr(X = 3) = (2/6) + (1/6) = 3/6
    - Pr(X ≤ 4) = Pr(X ≤ 3) + Pr(X = 4) = (3/6) + (1/6) = 4/6
    - Pr(X ≤ 5) = Pr(X ≤ 4) + Pr(X = 5) = (4/6) + (1/6) = 5/6
    - Pr(X ≤ 6) = Pr(X ≤ 5) + Pr(X = 6) = (5/6) + (1/6) = 1


---------------------
#### links:
[[]]
[[]]