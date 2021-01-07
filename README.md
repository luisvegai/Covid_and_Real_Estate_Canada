![housing market](/Resources/housing%20market.jpg)


# **Modelling housing market during COVID-19**

Links to Google Slides:

- [Project presentation](https://docs.google.com/presentation/d/1XloGJetDxiyN7Yh3OSNy-hipRLcIVP5_HimekSp4Ru0/edit?usp=sharing)

- [Dashboard (Blueprint)](https://docs.google.com/presentation/d/1xjqhkGYUn4ZUA-6dhtKq79eNqyQp06-95V_FGOHLePA/edit?usp=sharing)
<br>
<br>
<br>

## **1._Description of the project** <br>
<br>

### *Overview*<br>
In Canada, the job market is remarkably concentrated in the big cities of the provinces across the country. This situation leads to higher demand of real state and rent activity in such cities, and many developers rely on such predictable outcome to invest. However, the economy in 2020 has been deeply affected by the COVID-19 pandemic which forced many to work from home, being no longer necessary to look for lodging in the big cities. In this situation, it is important for private developers to know if COVID-19 has affected significantly the housing market in big and small cities across Canada. We are aiming to provide insight on how much the real estate market has changed in the months of the pandemic using as an indicator the **House Price Index (HPI)**. We will develop a tool to visualize the HPI values in the pandemic months compared to the "business-as-usual" values which we predict by modeling using a machine learning algorithm approach.
<br>
We finally would like to include an interactive dashboard from which the user can see the results of such comparison.
<br>
### *The questions we hope to answer are: <br>*

- How was the real estate market impacted by COVID-19?
- Does the city size in terms of population density play a role in this impact?
<br>

### *Data sources: <br>*

We will use data from 3 differents sources: <br>

- [Canadian Mortgage and Housing Corporation](https://www.cmhc-schl.gc.ca/en/data-and-research) <br>
- [Statistics Canada](https://www150.statcan.gc.ca/n1/en/type/data?subject_levels=46) <br>
- [Canadian Real Estate Association](https://creastats.crea.ca/en-CA/) <br>
<br>

### *Produced Database samples:*

New housing prices (price_index_clean.csv) <br>
Canadian population 2011-2016 (cleaned_canada_pop_2011_2016.csv)
<br>
<br>
<br>
## **2._Process**<br>
<br>

A combination of unsupervised and supervised machine learning techniques will be used to gain a better understanding of the impact that Covid-19 has had on the real estate market. Unsupervised machine learning was used to first identify any strong relationships between features, and then supervised machine learning will be used to build a model which predicts the HPI for a particular city. Furthermore, this prediction can be later compared to the actual HPI in 2020 and determine if a particular city's real estate market was impacted.<br>
<br>
### **Part 1: Unsupervised machine learning**
<br>

### * *Jupyter notebooks:*

    Unsupervised Modelling - rev7 - Housing.ipynb
    Unsupervised Modelling - rev7 - Land.ipynb
<br>

### *Model characteristics:*


-**Independent variables**: <br>
Price Index (HPI), Population Density, Year.<br>

-**Model algorithm**: K-means <br>
<br>
### * *Analysis of results*

Two separate analyses were performed using unsupervised machine learning. We analized separately the data for "land" and "home" housing type . Identified clusters are not clearly separated in the 3D plots for the two analyses, however some tendencies can be identified.<br>
<br>
For the "Land" housing type data, we observed that in recent years the HPI has remained mostly steady while most of the points are concentrated in medium size cities and lower, with no particular change for the year 2020.
<br>
<br>
Figure 1. Unsupervised machine learning result visualization - Land housing type
![Unsupervised machine learning result visualization - Land](/Resources/Unsupervised_ML_plot_land.PNG)
<br>
<br>
<br>As for the "Home" housing type data, it can be seen that a shift towards medium sized cities has been taking place over the past few years, with some points with lower HPI, and such tendency has been exacerbated in 2020.<br>
<br>
Figure 2. Unsupervised machine learning result visualization - Home housing type
![Unsupervised machine learning result visualization - Home](/Resources/Unsupervised_ML_plot_housing.PNG)
<br>
<br>
To improve this analysis, more features, such as city economic health factors should be considered.<br>
<br>
### **Part 2: Supervised machine learning**
<br>

### * *Jupyter notebooks:*

    Supervised Modelling - rev1 - Homes.ipynb 
    Supervised Modelling - rev1 - Land.ipynb
<br>
Supervised machine learning (Neural Networks) were used to initially build a model, but due to the low accuracy of the preliminary models, a simpler supervised machine learning technique such as multiple variable linear regression was chosen.<br>
<br>
We divided our 2015-2019 data into training and evaluation subsets in order to predict Price-Index without the effect of the 2020 pandemic.<br>
<br>
Low fit factors were obtained, implying that this analysis, although better than neural networks, still doesn't accurately depict a relationship between the features and the dependent variable (HPI).<br>
<br>
<br>

### *Analysis of results*
<br>

In the case of "Land" Housing type model, the coefficients tell us that the HPI has been increasing through the years, and that there is a slow market movement towards cities with high populaiton density.
<br>
<br>Fig. 3. Supervised machine learning result summary - Land housing type

![Supervised machine learning result summary - Land](/Resources/Supervised_ML_Summary_Land.PNG)
<br>
<br>As for the case of "House" Housing type model, the coefficients suggest also an increase of the HPI through the years. Nothing statistically sound can be said about the relationship between the population density and the HPI.
<br>
<br>Fig. 4. Supervised machine learning result summary - Home housing type

![Supervised machine learning result summary - Home](/Resources/Supervised_ML_Summary_Housing.PNG)
<br>
<br>
## **3._Conclusion**<br>
<br>
Overall, although both models has limitations given that the required data is hard to access, they can tell us that the House Price Index (HPI) had a tendency to increase through the years up to 2019, a year before the 2020 COVID-19 pandemic. Moreover, the data exploration phase showed us that in 2020 there was a shift towards medium sized cities in 2020 (COVID19 pandemic period) while HPI's increase rate has decreased. This suggests that the house market was indeed impacted, although as mentioned above, further features need to be considered to improve the models accuracy.<br>
<br>
<br>

## **Dashboard**

<br>
The dashboard link is noted below:
<br>
<br>
VARIATION OF HOUSE PRICE INDEX PER CITY

http://hpi-pred-app.herokuapp.com/
<br>
