
Tags: #python 

------------------------------------------
### Pandas

- CSV
    
    CSV stands for "Comma Separated Values". It is a file format used to store and exchange data in a table-like structure. Each line in the file represents a row in the table, and the values in the row are separated by commas. CSV files can be opened and edited in text editors or spreadsheet software such as Microsoft Excel. They are commonly used for data analysis and machine learning applications.
    
- why pandas?
    
    Pandas is a popular Python library for data manipulation and analysis. It provides powerful tools for working with structured data, such as tables or spreadsheets. Here are some scenarios where using Pandas may be suitable:
    
    1. Data Cleaning and Preprocessing: Pandas is great for cleaning and transforming data. It provides functions for dealing with missing values, converting data types, and reshaping data.
    2. Exploratory Data Analysis: Pandas provides a variety of functions for exploring data, such as grouping data, aggregating data, and filtering data. These functions can help you understand the relationships between different variables in your data.
    3. Data Visualization: Pandas can also be used to create visualizations of your data. It provides integration with popular visualization libraries such as Matplotlib and Seaborn.
    4. Data Integration: Pandas can be used to combine data from different sources, such as CSV files, Excel spreadsheets, and SQL databases.
    5. Machine Learning: Pandas can be used to prepare data for machine learning algorithms. It can be used to encode categorical variables, scale numerical variables, and split data into training and testing sets.
    
    Overall, if you need to work with structured data, whether it's for cleaning, analysis, or machine learning, Pandas can be a powerful tool to help you get the job done efficiently.
    
    [data:image/svg+xml,%3csvg%20xmlns=%27http://www.w3.org/2000/svg%27%20version=%271.1%27%20width=%2730%27%20height=%2730%27/%3e](data:image/svg+xml,%3csvg%20xmlns=%27http://www.w3.org/2000/svg%27%20version=%271.1%27%20width=%2730%27%20height=%2730%27/%3e)
    
    [https://chat.openai.com/_next/image?url=https%3A%2F%2Flh3.googleusercontent.com%2Fa%2FAEdFTp4pIUjtihJungNWQbviKId9lK_NOmae0Kdg86lg9g%3Ds96-c&w=64&q=75](https://chat.openai.com/_next/image?url=https%3A%2F%2Flh3.googleusercontent.com%2Fa%2FAEdFTp4pIUjtihJungNWQbviKId9lK_NOmae0Kdg86lg9g%3Ds96-c&w=64&q=75)
    
    in python , will pandas work with unstructured data
    
    Pandas is primarily designed to work with structured data, such as tables or spreadsheets, that have a well-defined set of columns and data types. However, pandas can also be used to work with unstructured data to some extent. Here are some examples:
    
    1. Text data: Pandas can work with text data in various formats, such as CSV, Excel, or JSON. You can use pandas to read in text data and convert it into a structured format that can be analyzed further. Pandas also provides functions for string manipulation, such as splitting or joining strings.
    2. Time-series data: Pandas has robust functionality for working with time-series data, which can be considered semi-structured data. You can use pandas to read in time-series data, apply various time-series analysis techniques, and perform forecasting.
    3. Images and Audio: Pandas does not have built-in functionality for working with images or audio data, which are typically considered unstructured data. However, you can use other Python libraries, such as Pillow or OpenCV, to read in and manipulate images, and librosa for audio data. Then you can use pandas to organize and analyze the extracted features.
    
    In summary, while pandas is primarily designed for structured data, it can be used to work with some types of unstructured data, especially when combined with other libraries. However, other specialized libraries may be more suitable for specific types of unstructured data.
    
- Data Frame Vs Series
    
    **`pandas.core.frame.DataFrame`** is a class in the Pandas library that represents a two-dimensional, size-mutable, tabular data structure with labeled axes (rows and columns). It is one of the core data structures in Pandas and is used to store and manipulate data in a variety of formats, such as CSV, Excel, SQL, and more.
    
    A DataFrame consists of rows and columns, where each column can have a different data type. The rows are labeled with an index, which can be either integers or strings, and the columns are also labeled with unique strings called column names. This makes it easy to access and manipulate data in a DataFrame using row and column labels.
    
    Data Frame Vs Series 
    
    The **`pandas.core.frame.DataFrame`** class represents a two-dimensional, size-mutable, tabular data structure with labeled axes (rows and columns) in Pandas. On the other hand, **`pandas.core.series.Series`** represents a one-dimensional, labeled array that can hold data of any type, such as integers, floats, strings, or objects.
    
    Here are some key differences between DataFrames and Series:
    
    1. Dimensions: The main difference between DataFrames and Series is that DataFrames have two dimensions (rows and columns), while Series have only one dimension (rows). This means that DataFrames can represent more complex and structured data than Series, which are more suitable for simple arrays.
    2. Indexing: While both DataFrames and Series have row labels, DataFrames also have column labels. This means that DataFrames can be accessed and manipulated using both row and column labels, whereas Series can only be accessed using row labels.
    3. Data types: DataFrames can contain columns of different data types, while Series can only contain data of a single data type. This makes DataFrames more flexible for handling complex data structures.
    4. Data alignment: DataFrames automatically align data based on both row and column labels, while Series align data based on only row labels. This makes it easier to perform arithmetic and logical operations on DataFrames.
    
    In summary, DataFrames are a more complex and powerful data structure in Pandas, designed to handle two-dimensional, labeled data with multiple data types, while Series are a simpler, one-dimensional data structure that is more suitable for working with simple arrays of data with a single data type.
    
- int64 & float64
    
    In Python, **`int64`** and **`float64`** are not types built into the language. However, they are data types that are commonly used in numerical computing libraries like NumPy and Pandas.
    
    **`int64`** refers to a 64-bit integer data type, which can represent integer values ranging from -2^63 to 2^63-1. The **`int64`** data type is useful for storing large integer values, particularly in numerical computations where precision is important.
    
    **`float64`** refers to a 64-bit floating-point data type, which can represent decimal values with up to 15-17 digits of precision. The **`float64`** data type is useful for storing decimal values that require a high degree of precision, such as in scientific and financial applications.
    
    In general, when working with numerical data in Python, it is important to choose the appropriate data type based on the range and precision of the values being represented. Choosing the right data type can help avoid issues with rounding errors, overflow, and underflow that can occur when using data types with limited precision.
    
- iloc vs loc
    
    In Pandas, `loc` and `iloc` are two methods for indexing and selecting data in a DataFrame.
    
    `loc` is primarily label-based, which means that you use row and column labels to select data. You can use `loc` to select rows and columns by label, or you can use boolean indexing to select data that meets certain conditions.
    
    On the other hand, `iloc` is primarily integer-based, which means that you use integer indexes to select data. You can use `iloc` to select rows and columns by integer position, or you can use boolean indexing to select data that meets certain conditions.
    
    To illustrate the difference, consider a simple DataFrame with row and column labels:
    
    ```python
    import pandas as pd
    
    df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6], 'C': [7, 8, 9]}, index=['a', 'b', 'c'])
    
    ```
    
    Using `loc`, you can select data by label like this:
    
    ```python
    df.loc['a', 'B']   # returns 4
    
    ```
    
    Using `iloc`, you can select data by integer position like this:
    
    ```python
    df.iloc[0, 1]   # returns 4
    
    ```
    
    In general, you should use `loc` when you want to select data by label, and `iloc` when you want to select data by integer position. However, both methods can be used interchangeably in some cases, and it's up to you to decide which method to use based on your specific needs.
    
- join vs merge
--------

### Exporting Files:
#### To CSV:

```
df.to_csv(path, index = False)
```

The `dataframe.to_csv()` function in Pandas is used to export a DataFrame to a CSV file. The function takes a number of arguments, including:

- `path_or_buf`: The path to the CSV file to be created, or a file-like object. If `None`, the CSV data is returned as a string.
- `sep`: The delimiter to use between columns. The default is a comma.
- `na_rep`: A string to represent missing values. The default is an empty string.
- `float_format`: A format string for floating-point numbers. The default is `%.6f`.
- `header`: Whether to include the column names in the output. The default is `True`.
- `index`: Whether to include the row index in the output. The default is `True`.

For example, to export a DataFrame called `df` to a file called `output.csv`, you would use the following code:

Code snippet

```
df.to_csv('output.csv')
```

This would create a file called `output.csv` with the following contents:

Code snippet

```
a,b,c
1,2,3
4,5,6
```

You can also pass a file-like object to the `path_or_buf` argument. For example, to export the DataFrame to a buffer in memory, you would use the following code:

Code snippet

```
with io.BytesIO() as buf:
    df.to_csv(buf)

csv_data = buf.getvalue()
```

The `csv_data` variable would now contain the CSV data as a string.

The `dataframe.to_csv()` function is a powerful tool for exporting DataFrames to CSV files. It can be used to save data for later analysis, or to share data with others.











---------------------

#### links:
[[]]
[[]]
### Useful Block of Code:
#### To drop perticular feature:
```python
df = df.drop('col3', axis=1) # axis = 1 column, axis = 0 rows
```
#### To rename features in bulk:
```python

new_names = {'feature_1': 'new_name_1', 'feature_2': 'new_name_2', 'feature_3': 'new_name_3'}
df = df.rename(columns=new_names)

```
