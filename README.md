![housing market](https://github.com/lskerrett/Covid-and-Real-Estate-Canada/blob/master/Resources/housing%20market.jpg)


# **Modelling change of housing market due to COVID-19**

## **1._Description of the project**

### *Overview*
In Canada, the job market is remarkably concentrated in the big cities of the provinces across the country. This situation leads to higher demand of real state and rent activity in such cities, and many developers rely on such predictable outcome to invest. However, the economy in 2020 has been deeply affected by the COVID-19 pandemic which forced many to work from home, being no longer necessary to look for lodging in the big cities. In this situation, it is important for private developers to know if COVID-19 has affected significantly the housing market in big and small cities across Canada.

### *The questions we hope to answer are: <br>*

- Did the real state market was impacted positively or negatively by COVID-19?
- Is the impact different in small cities and big cities?
 
### *Data sources*

We will use data from 3 differents sources: <br>

-[Canadian Mortgage and Housing Corporation](https://www.cmhc-schl.gc.ca/en/data-and-research) <br>
-[Statistics Canada](https://www150.statcan.gc.ca/n1/en/type/data?subject_levels=46) <br>
-[Canadian Real Estate Association](https://creastats.crea.ca/en-CA/) <br>
-
### *Data base samples:*
Housing inventory (housing_inventory_clean_v2.csv) <br>
New housing prices (price_index_clean.csv) <br>
Canadian population 2011-2016 (cleaned_canada_pop_2011_2016.csv)<br>

### *Communication*

Communication will be done via Slack and Zoom. We will carry out online meetings at least twice a week with all members.

## **2._Process**

A combination of unsupervised and supervised machine learning techniques will be used to gain a better understanding of the impact that Covid-19 has had on the real estate market. Unsupervised machine learning will be used to first identify any strong relationships between features, and then supervised machine learning will be used to build a model which predicts the housing price index for a particular city. This trained supervised machine learning model will then be used to predict potential cities that have high chances of having their housing price index increase. 

### **Part 1: Unsupervised machine learning**

### *Model characteristics:*

-**Dependent variable:** House price index <br>

-**Independent variables** (categorical variables were encoded): <br>
Housing_type, Price_index, city_size_type, population_2016,city_type, population_density, Ref_Date_y, completed_units, Dwelling_type, Unit_Value    <br>

-**Model algorithm**: K-means <br>

### *Analysis of results*

Clusters were not clearly identified in the 3D plot of the first 3 principal components. Variance explained by the 3 first principal components are 0.01278873, 0.0088067 , and 0.00812733.

### *Next steps:*

Supervised machine learning (Neural Networks for example) will be used to build a model which predicts the housing price index for a particular city. This model will be trained with data for years before 2020 and then used to predict house price index for the year 2020 which is when the COVID-19 pandemic happened. We will then analize if the difference between the predictions and the actual house price index for the year 2020 are statistically significant or not. If the difference is statistically significant, this could suggest an effect on house price index due to COVID-19.