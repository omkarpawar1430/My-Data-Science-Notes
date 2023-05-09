
Tags: #stats

------------------------------------------
Kurtosis is a statistical measure that describes the shape of a distribution. Specifically, it measures the degree of peakedness (i.e., the height and sharpness of the central peak) and the thickness of the tails (i.e., the degree to which the data points extend far from the central peak) of a distribution.

A distribution with high kurtosis has a sharp peak and heavy tails, which means that there are more extreme values in the dataset. On the other hand, a distribution with low kurtosis has a flatter peak and lighter tails, which means that the data points are more spread out and there are fewer extreme values.

There are different ways to calculate kurtosis, but the most common method is to use the fourth moment about the mean. The formula for calculating kurtosis is:

`Kurtosis = (1/n) * sum((xi - mean) ** 4) / (sigma ** 4) - 3`

where `n` is the sample size, `xi` is each data point, `mean` is the sample mean, and `sigma` is the sample standard deviation. The value of kurtosis can be positive, negative, or zero.

A normal distribution has a kurtosis value of 3, which is subtracted from the calculated value of kurtosis to obtain the excess kurtosis. Excess kurtosis is a measure of kurtosis relative to a normal distribution, with positive values indicating a more peaked distribution and negative values indicating a flatter distribution.

In summary, kurtosis is a statistical measure that describes the shape of a distribution by measuring the degree of peakedness and the thickness of the tails. It is useful for understanding the distribution of a dataset and identifying any potential issues such as outliers or data points that are too extreme.


```python

import pandas as pd
from scipy.stats import skew, kurtosis

# Load the Boston Housing dataset into a pandas dataframe
df = pd.read_csv('Boston.csv')

# Calculate the skewness and kurtosis for each feature
for col in df.columns:
    if col != 'MEDV':  # Skip the target variable
        skewness = skew(df[col])
        kurt = kurtosis(df[col])
        print(f'{col}: Skewness = {skewness:.2f}, Kurtosis = {kurt:.2f}')

```

---------------------
#### links:
[[]]
[[]]