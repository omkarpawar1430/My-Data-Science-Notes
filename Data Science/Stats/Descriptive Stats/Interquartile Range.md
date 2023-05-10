
Tags: #stats 

------------------------------------------

The interquartile range (IQR) is a measure of the spread or dispersion of a dataset. It is calculated as the difference between the third quartile (Q3) and the first quartile (Q1) of the dataset. In other words, IQR represents the range of the middle 50% of the data.

1. Arrange data in order
2. Find median of dataset = Q2
3. Find median of the first half of the dataset = Q1
4. Find median of the second half of the dataset = Q3
5. IQR = Q3 - Q1

	Q1 = median of first 50 % of data
	Q2 = median of 100% of data
	Q3 = median of second 50 % data

$IQR = Q3 - Q1 = 39 - 20 = 19$

![https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2018/03/interquartile_range.png?w=576&ssl=1](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2018/03/interquartile_range.png?w=576&ssl=1)

![https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2021/08/IQR_example.png?w=199&ssl=1](https://i0.wp.com/statisticsbyjim.com/wp-content/uploads/2021/08/IQR_example.png?w=199&ssl=1)

IQR can be used in a variety of statistical analyses, including box-and-whisker plots, which are graphical representations of the distribution of the data. IQR can also be used to detect and analyze differences in variability between different groups or subgroups in a dataset.

IQR is a useful measure of dispersion because it is not sensitive to outliers or extreme values in the dataset, unlike range or standard deviation. It provides a robust measure of the variability of the data that can help identify the middle 50% of the data points.

--- 

the lower fence is defined as:

`lower fence = Q1 - k * IQR`

and the upper fence is defined as:

`upper fence = Q3 + k * IQR`

where `Q1` and `Q3` are the first and third quartiles of the data, respectively, and `IQR` is the interquartile range, defined as `IQR = Q3 - Q1`. The value `k` is a constant that determines how far the fences are from the quartiles, and is typically set to 1.5 in the Tukey method.

We can identify outliers from our dataset using Upper fence and lower fence 
##### Demo Code:
```python
for k, v in data.items():

# k - Feature , v - values from that feature

q1 = v.quantile(0.25)

q3 = v.quantile(0.75)

irq = q3 - q1 # Inter Quartile Range

# | - OR

# we are creating list of elements for particular features which are outside of IQR

v_col = v[(v <= q1 - 1.5 * irq) | (v >= q3 + 1.5 * irq)]

perc = np.shape(v_col)[0] * 100.0 / np.shape(data)[0]

print("Column %s outliers = %.2f%%" % (k, perc))

```


---------------------
#### links:
[[]]
[[]]