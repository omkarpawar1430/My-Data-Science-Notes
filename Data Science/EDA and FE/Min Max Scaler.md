
Tags: #eda 

------------------------------------------
- It is used when data don't have the same scale
- Remember to apply the scaling separately to the training and testing data to avoid **data leakage** and maintain the integrity of your evaluation process.
- scales the values between fixed range of [0,1]. 
- 
----------
In EDA (Exploratory Data Analysis), it is common to normalize or scale the features in a dataset so that they have a similar range of values. This is done to avoid the issue of certain features dominating the analysis simply because they have larger values. Min-Max scaling is a common method for scaling numerical features in a dataset.

The Min-Max scaler scales the values of a feature to a fixed range of [0,1], based on the minimum and maximum values of that feature in the dataset. The formula for Min-Max scaling is:

>`X_scaled = (X - X_min) / (X_max - X_min)`
>
>where X is the original value of the feature, X_min and X_max are the minimum and maximum values of the feature in the dataset, and X_scaled is the scaled value of the feature.

Min-Max scaling has the benefit of preserving the shape of the original distribution of the feature values, while also scaling them to a fixed range. This makes it easier to compare and visualize the features in the dataset.

Here's an example code snippet using the `MinMaxScaler` class from `sklearn.preprocessing` to perform Min-Max scaling on a DataFrame:

```python

from sklearn.preprocessing import MinMaxScaler
import pandas as pd

# create a sample DataFrame
data = pd.DataFrame({'feature_1': [1, 2, 3, 4, 5], 'feature_2': [10, 20, 30, 40, 50]})

# initialize the MinMaxScaler
scaler = MinMaxScaler()

# fit and transform the data
scaled_data = scaler.fit_transform(data)

# create a new DataFrame with the scaled data
scaled_df = pd.DataFrame(scaled_data, columns=data.columns)

# print the original and scaled DataFrames
print('Original Data:\n', data)
print('\nScaled Data:\n', scaled_df)

```


In this example, we create a sample DataFrame with two features, `feature_1` and `feature_2`. We then initialize the `MinMaxScaler` and fit and transform the data using the `fit_transform()` method. Finally, we create a new DataFrame with the scaled data and print both the original and scaled DataFrames.

The output of the code will be:

```Markdown

Original Data:
    feature_1  feature_2
0          1         10
1          2         20
2          3         30
3          4         40
4          5         50

Scaled Data:
    feature_1  feature_2
0        0.0        0.0
1        0.2        0.2
2        0.4        0.4
3        0.6        0.6
4        0.8        0.8

```

As you can see, the values of both features have been scaled to a fixed range of [0,1] based on the minimum and maximum values in the original dataset.


---------------------
#### links:
[[]]
[[]]