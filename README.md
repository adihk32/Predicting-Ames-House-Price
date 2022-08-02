# Project 2: Predicting Ames Housing Price using Regression Model

### Problem Statement:  

- As an analyst with MyHome, the aim of this study is to create a regression model to predict home sale prices based on the features of the property. And we would like to recommend top 4 features of the housing that can fetch higher sale prices for residential properties
---

### Background:
Having property is a milestone for every adult. But most people do not know what to look out for when they buy a property. In recent [study](https://www.cbsnews.com/news/home-house-prices-mortgage-rates-moodys-mark-zandi/) by Moody Analytics, 97% of residential properties are overvalued across the US. In other [study](https://www.cnbc.com/2022/05/01/survey-majority-of-homeowners-have-regrets.html), 20% of property buyer having regret on underestimating the cost of purchasing home. Thus, it is very important to know what you get for what you pay.

Meanwhile, if you have own a house and when you trying to sell it. Most of the time, the seller do not know how to price the property and tend to based on the trend of the property price around the neighborhood. If they are fortunate, they might sell at a fair value. While the unfortunate one, suffers from undervaluing their own property.

MyHome is an online property listing platform that connects home sellers with potential buyers. The website also provides data-driven recommendations on price trends based on details of the listings to help users optimise their bid/sell prices.

Based on an [article](https://homeia.com/10-important-features-to-consider-when-buying-a-house/), this are the top 10 features that is important when buying home:
1. Location
2. Lot Area
3. Number of Bedrooms
4. Number of Bathrooms
5. Kitchen Layout
6. Home Appliances Quality
7. Age of the House
8. **Price**
9. Seller's incentive
10. Maintenance Mode

Therefore, we will analyse and find out if those features is considered some of the high price features based on the dataset


### Datasets Selected:
We will be using Ames Housing Data Set that has transaction details at Ames, IOWA for the period of 2006 to 2010. The dataset is split into two sections:
* [`train.csv`](datasets/train.csv): Transaction details for housing in Ames from 2006-2010 as a train set
* [`test.csv`](datasets/test.csv): Remaining transaction details for housing in Ames from 2006-2010 as a test set
---

### Data Dictionary:

You can find the data dictionary in the [link](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt).

---

### Executive Summary: 
- Most of the features have skewed distribution. This may make the model to predict less accurate.
- Among the nominal features, we have chosen House Style, Foundation Type, Neighborhood, Masonry Veneer Type to be included in the model. We further catagorise them to relevant categories and dummified the features before inputting them to the model
- As for the numerical features, ordinal and continuous features, we found that the quality for every aspect of the house have a high correlation with sale price. The area of the interior also has a high correlation to the sale price.
- Other new engineered features, such as Total Bathroom, Age, and Area to Room Ratio were found to be correlated with the sale price.
- Total of 26 features, including dummies, are selected for the model fitting
- After fitting and scaling the data, we try to model on three types of regression: linear regression, lasso regression and ridge regression.
- Based on prediction, here are the RMSE for all the models:
|Model|R2 Score|RMSE Score|
|---|---|---|
|Linear Regression|0.826304|22393.5604|
|Lasso Regression|0.825742|22393.2017|
|Ridge Regression|0.826154|22392.0939|

- Ridge regression provides the best R2 score and also lowest RMSE Score on the X_test data. Thus, ridge regression is selected.
- The coefficient value reveals that the top features are: Interior Living Area, Overall Quality, Neighborhood, Basement Quality&Height, Garage Area and Kitchen Quality. 
- Poured Concrete foundation has a higher value compared to other type of foundation
- 1st Story house is valued highest compared to other style.
---

### Conclusions/Recommendations:

**Conclusions :**
- Ridge regression has the best fit for the features and dataset
- Area of the interior has a big part in determining the Sale Price
- The location which has the highest price value would be at the North Area
- Kitchen and Fireplace also play big part in the Sale Price
- The more the bathroom is the higher the property is valued
- Renovation will help to increase the price as well
- The top features coincide with most of the features mentioned in the list at the Background part

**Recommendations :**  
For buyers:
- To invest in renovation 
- To purchase (for investment):
 > - A bigger living area
 > - House located in the North of Iowa State University
 > - House with higher basement
 - For budget constraint, can go for property at the East for relative cheaper price
 
 For sellers:
- To highlight the quality of the house
- To highlight the basement quality and area
- To ask for a better price if the house is at the North side and has big living area

**Limitations :**
- The time range of the data only include transaction from 2006 to 2010
- The data only includes the transaction in the city of Ames
- Most of the features have a skewed data where one type of the value hold the majority counts

**Future Works :**
- Implement the model to the latest transaction data to check if the trends still holds
- Implement the model with the data from other city in the United States to get overview trends for US
- Implement the model with variability on the value, especially the nominal and categorical features
---