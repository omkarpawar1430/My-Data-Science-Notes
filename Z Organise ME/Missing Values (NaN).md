------------------------- 
Tags: #eda 
⏰ Date Created:  2023-09-16, @ 13:02

---
>[!info] Keywords
>* 
>* 


Missing values can carry information when their presence or absence is not random but instead related to some underlying pattern or condition in the data. Understanding these patterns can be crucial for making informed decisions during data analysis. 

**Example: Loan Default Prediction**

Suppose you are working on a dataset related to loan applications, and one of the features is "Credit Score." The dataset contains information about whether applicants defaulted on their loans (1 for default, 0 for no default) and other relevant details.

In this scenario, missing values in the "Credit Score" column can carry valuable information. Here's how:

1. **Missing Completely at Random (MCAR):**
   - If the missingness of credit scores is entirely random, it may not carry any information. In this case, you could impute missing values using methods like mean, median, or a machine learning model without introducing bias.

2. **Missing at Random (MAR):**
   - However, if the missingness of credit scores is related to another observed variable, it can carry information. For instance, imagine that borrowers with high incomes are more likely to have their credit scores reported because they often apply for larger loans. In contrast, borrowers with lower incomes may not have their scores reported because they seek smaller loans and are less likely to default.

   - In this scenario, the presence or absence of a credit score can inform us about the income level of the applicants. Borrowers with missing credit scores may be more likely to be in the lower-income group, and this can be important information for assessing their creditworthiness. You could impute the missing values by considering this relationship with income.

3. **Missing Not at Random (MNAR):**
   - Sometimes, missing values are related to the unobserved or unrecorded factors. For example, applicants with a history of financial delinquency may intentionally avoid reporting their credit scores to improve their chances of loan approval. In this case, missing credit scores carry information about the applicants' credit history, which is not explicitly recorded.

   - Handling MNAR data is challenging because the missingness is not related to the observed variables in the dataset. However, it's essential to recognize the potential information in these missing values and consider it when making decisions.

In summary, missing values can carry information when their presence or absence is related to some underlying factors or patterns in the data. Understanding the nature of missingness is crucial for making informed choices about how to handle missing data during data analysis and modeling. It may involve using domain knowledge, statistical methods, or machine learning techniques to account for the information carried by missing values.

```python
# To check/visualize nan values for EDA:
def percent_missing(df):
	percent_nan = 100*df.isnull().sum()/len(df)
	percent_nan = percent_nan[percent_nan > 0].sort_values()
	return(percent_nan)

percent_nan = percent_missing(df)

import seaborn as sns
import matplotlib.pyplot as plt

sns.barplot(x=percent_nan.index, y=percent_nan)
plt.xticks(rotation=90)
plt.show()
```

### Interview Questions:



>[!summary] 
>1. 
>2. 

----
>[!cite]
> 🤝 Connect with Me: https://www.linkedin.com/in/omkarpawar1430/
> 💗 Subscribe to our YouTube Channel: https://www.youtube.com/@datadecides

