
Tags: #stats 

------------------------------------------

==Variance is spread of data around the mean==. **A high variance indicates that the data points are spread out over a wide range of values, while a low variance indicates that the data points are clustered closely around the mean.****

Variance can be a useful tool in data analysis, but it is important to keep in mind that it can be **sensitive to outliers or extreme values in the dataset.** In such cases, it may be more appropriate to use other measures of dispersion, such as the interquartile range, which are less sensitive to outliers.

- population variance
    
    To find the variance, take a data point, subtract the population means, and square that difference. Repeat this process for all data points. Then, sum all of those squared values and divide by the number of observations. Hence, it’s the average squared difference.
    
     
- sample variance
    
    The calculation process for samples is very similar to the population method. However, you’re working with a sample instead of a population, and you’re dividing by ==n–1==. This denominator counteracts a bias where samples tend to underestimate the population value.
    
    ![https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2021/11/sample_variance_formula.png?resize=211,79&is-pending-load=1#038;ssl=1](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2021/11/sample_variance_formula.png?resize=211,79&is-pending-load=1#038;ssl=1)
    
    By dividing by n - 1 instead of n, we are effectively "penalizing" the sample variance slightly to account for the fact that we are estimating the population variance using only a subset of the data. This adjustment makes the sample variance a more accurate estimate of the population variance, and it also ensures that the variance estimate is unbiased.
    
    In summary, **we divide by n - 1 instead of n when we calculate sample variance because we need to adjust the calculation to account for the fact that we have one less degree of freedom than we would if we had the full population data**. This adjustment makes the variance estimate more accurate and ensures that it is an unbiased estimator of the population variance.


![https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2018/03/Variance_worksheet.png?w=336&ssl=1](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2018/03/Variance_worksheet.png?w=336&ssl=1)


- NOTE: all the data point are in the range of  11 to 58 yet variance is 201. To eliminate it we can use [[Standard Deviation]].
---------------------
#### links:
[[Standard Deviation]]
[[Coefficeint of Variance]]
