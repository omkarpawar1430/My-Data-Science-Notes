#stats 

-----------------

- Doubts
        
        - p values extra
            
            When we conduct a statistical test, we are trying to determine whether the results we obtained from our sample data are likely to have occurred by chance or if they represent a real difference or effect in the population. The significance level is a threshold that we set to help us make this determination.
            
            If the p-value (the probability of obtaining the observed results or more extreme results, assuming the null hypothesis is true) is less than or equal to the significance level (usually set at 0.05 or 0.01), we conclude that the results are statistically significant. This means that the likelihood of obtaining these results by chance alone, assuming the null hypothesis is true, is very small. We reject the null hypothesis and accept the alternative hypothesis, which suggests that there is a real difference or effect in the population.
            
            On the other hand, if the p-value is greater than the significance level, we cannot conclude that the results are statistically significant. This means that the likelihood of obtaining these results by chance alone, assuming the null hypothesis is true, is high. In this case, we fail to reject the null hypothesis, which suggests that there is no real difference or effect in the population.
            
            In simpler terms, if the p-value is less than or equal to the significance level, we have strong evidence to support our hypothesis that there is a real difference or effect. If the p-value is greater than the significance level, we do not have enough evidence to support our hypothesis and we must conclude that our results may have occurred by chance.
            
        Choosing the appropriate significance level depends on the research question and the consequences of making a Type I error (rejecting the null hypothesis when it is true). A lower significance level decreases the chance of making a Type I error but increases the chance of making a Type II error (failing to reject the null hypothesis when it is false).
        
    - Sampling Error - CLT
    - P value
    
    ### Confidence Interval
    
    In statistics, a confidence interval is a range of values that is likely to contain an unknown population parameter with a certain level of confidence.
    
    In data science, the confidence interval is a common tool used to estimate the precision and reliability of an estimate or prediction made from a sample of data. Specifically, it tells us how much variation we can expect if we were to take multiple random samples of the same size from the same population.
    
    The confidence interval is calculated from the sample data using a specified level of confidence and a statistical formula that takes into account the sample size and variability. The result is a range of values around the sample estimate, typically expressed as a lower and upper bound.
    
    For example, if we have a sample mean of 50 with a 95% confidence interval, we can say that we are 95% confident that the population mean lies somewhere between a lower bound of, say, 45 and an upper bound of 55. The wider the confidence interval, the less precise our estimate is likely to be, while a narrower interval suggests a more precise estimate.
    
    The level of confidence chosen is typically 90%, 95%, or 99%, with a higher confidence level meaning a wider interval. Choosing the appropriate confidence level depends on the context and the consequences of making an incorrect inference.
    
    In summary, the confidence interval is a useful statistical tool in data science that allows us to estimate the range of values where we can expect the true population parameter to lie, given a sample of data and a specified level of confidence.
   

### Central Limit Theorem

The central limit theorem (CLT) is a fundamental concept in statistics that states that when the sample size of a population is large, the distribution of sample means will be approximately normal, regardless of the distribution of the population from which the samples were taken.

For example, imagine you wanted to know the average height of people in a particular city. You could measure the height of every single person in the city, but that would be incredibly time-consuming and impractical. Instead, you could take a random sample of people from the city and calculate the average height of that sample. If you repeated this process many times with different samples each time, the distribution of the means would become more and more normal as the sample size increased, even if the population heights did not follow a normal distribution.

This is important because many statistical tests and models rely on the assumption that the data follows a normal distribution. By using the central limit theorem, even non-normally distributed data can be analyzed using these statistical methods.

- For Population data that is already normally distributed, You can have any sample size.
- For Population data that is not normally distributed, You should have a sample of greater than or equal to 30.

# Hypothesis Testing & Statistical Analysis


### [[Hypothesis Testing]]:






---------------------
#### links:
[[]]
[[]]