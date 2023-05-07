
Tags: #stats 

------------------------------------------

- [Exponential Distribuion](https://en.wikipedia.org/wiki/Exponential_distribution)
    - Key Idea
        
        The exponential distribution is a probability distribution that describes the time between events in a Poisson process, where events occur continuously and independently at a constant rate over time. The distribution is characterized by a single parameter, λ (lambda), which is the rate parameter or the mean number of events per unit of time. The exponential distribution is often used in reliability analysis, queuing theory, and other areas of applied statistics.
        
        The key components of the exponential distribution are:
        
        1. Probability Density Function (PDF): The PDF of the exponential distribution is given by f(x) = λe^(-λx), where x is the time between events. The PDF is zero for negative values of x and has a maximum value of λ at x = 0.
        2. Cumulative Distribution Function (CDF): The CDF of the exponential distribution is given by F(x) = 1 - e^(-λx), which represents the probability that an event occurs within time x. The CDF approaches 1 as x approaches infinity.
        3. Mean: The mean or expected value of the exponential distribution is equal to 1/λ, which represents the average time between events.
        4. Variance: The variance of the exponential distribution is equal to 1/λ^2, which indicates the spread or variability of the distribution.
        5. Memoryless Property: The exponential distribution has a unique property called memorylessness, which means that the probability of an event occurring within a fixed time interval does not depend on the amount of time that has elapsed since the last event. This property makes the exponential distribution useful in modeling processes that have no memory, such as the failure times of certain electronic components.
            - EXTRA
                
                For example, suppose we are interested in modeling the time until a light bulb fails, and we assume that the failure time follows an exponential distribution. If a light bulb has been in use for t hours without failing, the probability that it will fail within the next hour is the same as the probability that a new light bulb will fail within the first hour of use. The memoryless property of the exponential distribution means that the time the light bulb has already been in use does not affect the probability that it will fail within the next hour.
                
        6. Relationship dto Poisson Distribution: The exponential distribution is closely related to the Poisson distribution, which describes the number of events that occur in a fixed time interval. If the time between events follows an exponential distribution with rate parameter λ, then the number of events that occur in a time interval of length t follows a Poisson distribution with mean λt.



---------------------
#### links:
[[]]
[[]]



---


#### Links:
	[[]]