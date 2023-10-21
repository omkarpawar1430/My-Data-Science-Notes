
Tags: #stats 

------------------------------------------

## Types of Data:

![[Pasted image 20230506081535.png]]

### Categorical

Categorical data is data that is Just a label or a Name. e.g. colors, a brand of cars, gender. This type of data can not be compared with each other.

<aside>
🎯 eg. colors, brand names, gender

- Just a name
- No Order / Hierarchy
</aside>

### Numerical

- Discrete
    
    Discrete data refers to numerical data that can only take on specific values, typically integers, and cannot be expressed as fractions or decimals. Examples of discrete data include the number of children in a family, the number of cars in a parking lot, or the number of students in a classroom.
    
    <aside>
    🎯 Discrete data can be only expressed in the form of Whole numbers only. 
    0, 1, 2, …., n
    
    - we can have a finite number of data in a certain range
    - int
    </aside>
    
- Continuous
    
    Continuous data, on the other hand, refers to numerical data that can take on any value within a certain range. Continuous data can be expressed as fractions or decimals and is usually measured using a scale. Examples of continuous data include height, weight, temperature, or time.
    
    The main difference between discrete and continuous data lies in the nature of the measurement scale. Discrete data is measured on a nominal or ordinal scale, while continuous data is measured on an interval or ratio scale. Additionally, statistical methods used for discrete data are different from those used for continuous data.
    
    <aside>
    🎯 weight, height, Time, Area, Distance
    
    - we can have an infinite number of data in a certain range
    - float
    </aside>
    

## Measurement Levels

### Qualitative Data

- Nominal
    
    Nominal data is a type of categorical data where the data points represent categories or groups with no inherent order or ranking. Examples of nominal data include gender (male or female), eye color (brown, blue, green, etc.), or race/ethnicity (Asian, Black, White, etc.). Nominal data can be represented using labels, numbers, or symbols, but the order or ranking of the categories is not important.
    
- Ordinal
    
    Ordinal data is a type of categorical data that has an inherent order or ranking. However, the distance between values is not known or not meaningful. Examples of ordinal data include educational attainment (high school diploma, bachelor's degree, master's degree, etc.), or levels of satisfaction (very satisfied, somewhat satisfied, somewhat dissatisfied, very dissatisfied). Ordinal data can be represented using numbers or symbols, but the distance between values is not meaningful.
    

### Quantitative Data

- Interval
    
    Interval data is a type of numerical data where the distance between values is meaningful, but there is no true zero point. Examples of interval data include temperature measured in Celsius or Fahrenheit or time measured in hours or minutes. In interval data, the zero point is an arbitrary point and does not represent the complete absence of the quantity being measured.  the zero point is an arbitrary point and does not represent the complete absence of the quantity being measured.
    
    - e.g.
        
        let's consider the temperature measured in Celsius. If the temperature is 20°C and the temperature increases by 5°C, the new temperature would be 25°C. Similarly, if the temperature decreases by 5°C from 20°C, the new temperature would be 15°C. In interval data, the distance between values is meaningful, but 0°C does not represent the complete absence of temperature.
        
- Ratio
    
    Ratio data is a type of numerical data where there is a true zero point, which represents the complete absence of the quantity being measured. Examples of ratio data include height, weight, age, or income. In ratio data, the ratio between values is meaningful and can be used to make comparisons.
    
    - e.g.
        
        example of ratio data is age. If a person is 30 years old, and another person is 60 years old, we can say that the second person is twice as old as the first person. This is because age has a true zero point (birth), and the ratio between the two values is meaningful.
        
    

## Scales of Measurement

- Nominal Scale
    
    The nominal scale is the simplest level of measurement and is used for variables that have no inherent order or hierarchy. Examples of nominal scale include gender, race, or favorite color. In nominal scale, data are categorized or labeled with names or symbols, and these categories have no numerical value. It is not possible to calculate meaningful numerical statistics such as mean or median on nominal data.
    
    <aside>
    📌 1. No inherent order / Hierarchy
    2.  Just a Lable
    
    </aside>
    
- Ordinal Scale
    
    Ordinal scale is used for variables that have a natural order or hierarchy. Examples of ordinal scale include educational level (e.g., high school, bachelor's degree, master's degree), or rating scales (e.g., likert scales). In ordinal scale, data can be ordered, and the order matters, but the differences between categories are not necessarily equal. It is possible to calculate meaningful statistics such as median or mode on ordinal data, but not mean.
    
    <aside>
    📌 1. Oreder/ Hierarchy 
    2. Difference between two can not be calculated
    
    </aside>
    
- Interval Scale
    
    Interval scale is used for variables where the differences between values are equal, but there is no true zero point. Examples of interval scale include temperature measured in Celsius or Fahrenheit, or time measured in hours or minutes. In interval scale, data can be ordered, and the differences between categories are equal. It is possible to calculate meaningful statistics such as mean, median or mode on interval data.
    
    <aside>
    📌 1. Order/ Hierarchy
    2. Difference between two values is equal 
    4. Ratio can not be measured ( e.g. we can’t say that we are going to feel twice warm or cool based on temp ratio ) 
    3. No True  zero point ( e.g. even if the temperature is zero it’s still there and we can feel chill 🥶 )
    
    </aside>
    
- Ratio  Scale
    
    The ratio scale is used for variables where the differences between values are equal and there is a true zero point. Examples of ratio scale include height, weight, age, or income. In a ratio scale, data can be ordered, and the differences between categories are equal. It is possible to calculate meaningful statistics such as mean, median, mode or percentage on ratio data.
    
    <aside>
    📌 1. Order/ Hierarchy
    2. Difference between two values is equal
    3. True Zero Point ( e.g. if we are jobless we are not earning any money, and income is zero 🤕 )
    
    </aside>
    
- the temperature in all scales


![[Pasted image 20230506081619.png]]    
    

## Population and Sample Data

![https://s3-eu-west-1.amazonaws.com/blog.omniconvert.com-media/blog/wp-content/uploads/2019/10/21150245/sample-size-definition.png](https://s3-eu-west-1.amazonaws.com/blog.omniconvert.com-media/blog/wp-content/uploads/2019/10/21150245/sample-size-definition.png)

population data (N) vs Sample data (n)

In statistics, a population is a group of individuals, objects, or events that share a common characteristic of interest. Population data refers to data collected from the entire population of interest. On the other hand, a sample is a subset of the population that is selected for study or analysis. Sample data refers to data collected from a sample of the population.

To understand the difference between population data and sample data, let's consider an example:

Suppose a city government wants to estimate the average income of all residents in the city. The population in this case would be all the residents in the city. Collecting data from all residents in the city would be impractical and time-consuming. Therefore, the government can collect data from a representative sample of residents and use inferential statistics to estimate the average income of the entire population.

In this case, the sample would be a subset of residents selected to participate in the study. The sample data would be the income information collected from these selected residents. The sample data would be used to estimate the population parameter of interest, which is the average income of all residents in the city.

Population data and sample data are important concepts in statistics because they help us to make inferences about the entire population based on a smaller subset of data. It is important to carefully select the sample and ensure that it is representative of the population of interest to obtain accurate estimates and conclusions.

- Sampling Error
    
    The difference between the sample mean and the population mean is known as the sampling error, and it can be reduced by increasing the sample size. As the sample size increases, the sample mean will converge to the population mean, and the sampling error will decrease.
    

# Visual Representation of Data

## For Categorical

![[Pasted image 20230506081707.png]]

- Frequency Distribution Tables
    
    It’s a Tabular form of visualization with Category and it’s Frequency
    
- Bar Charts
    
    It’s a graphical form of visualization with Category and it’s the frequency  
    
- Pie Charts
    
    Its visualization with category By using its total contribution to the 100 Percentage of Data 
    
- Pareto Diagrams
    
    Its visualization of frequency and percentage at the same time. a bar chart is ordered from highest to lowest.  
    
    [https://www.jmp.com/en_nl/statistics-knowledge-portal/exploratory-data-analysis/pareto-chart.html#:~:text=Pareto charts show the ordered frequency counts of data&text=These charts are often used,“80%2F20” rule](https://www.jmp.com/en_nl/statistics-knowledge-portal/exploratory-data-analysis/pareto-chart.html#:~:text=Pareto%20charts%20show%20the%20ordered%20frequency%20counts%20of%20data&text=These%20charts%20are%20often%20used,%E2%80%9C80%2F20%E2%80%9D%20rule).
    
- Chat Gpt Ans:
    1. Bar Chart: A bar chart is one of the most common ways to visualize categorical data. It consists of a series of bars, with the length of each bar representing the frequency or proportion of each category.
    2. Pie Chart: A pie chart is another popular way to display categorical data. It is a circular chart that is divided into slices, with each slice representing a category. The size of each slice corresponds to the proportion of the category in the dataset.
    3. Stacked Bar Chart: A stacked bar chart shows the distribution of categories across two or more variables. The bars are stacked on top of each other, with each segment of the bar representing the proportion of a category for a specific variable.
    4. Treemap: A treemap is a hierarchical way to display categorical data. It shows the proportion of each category as a rectangle, with the size of the rectangle proportional to the category's frequency or proportion.
    5. Heatmap: A heatmap is a way to display categorical data in a two-dimensional grid. The grid cells are colored to indicate the frequency or proportion of each category.
    6. Wordcloud: A wordcloud is a visual representation of text data, where the size of each word corresponds to its frequency in the dataset. Wordclouds can be used to display categorical data that is in text form, such as customer reviews or survey responses.

## For Numerical

- Histogram { num }
    
    For numerical data, Histogram is used. Data is divided into intervals and their frequency is measured and data is represented. 
	![[Pasted image 20230506081729.png]]    
    
- Side-by-side chart { categorical data + num }
	![[Pasted image 20230506081752.png]]
- Scatter plot  { num x num }
    ![[Pasted image 20230506081819.png]]
---------------------
#### links:
