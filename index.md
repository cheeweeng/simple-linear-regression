---
title
---
# simple-linear-regression

This lab uses simple linear regression to explore the relationship between two continuous variables. 
The project will perform a complete simple linear regression analysis, which includes:  
1.  creating and fitting a model,
2.  checking model assumptions,
3.  analyzing model performance,
4.  interpreting model coefficients,
5.  communicating results to stakeholders.

This activity will develop your knowledge of linear regression and your skills evaluating regression results which will help prepare you for modeling to provide business recommendations in the future.  

This lab used the marketing and sales dataset which includes information about marketing campaigns across TV, radio, and social media, as well as how much revenue in sales was generated from these campaigns.
The features in the data are:
* TV promotion budget (in millions of dollars)
* Social media promotion budget (in millions of dollars)
* Radio promotion budget (in millions of dollars)
* Sales (in millions of dollars)

Each row corresponds to an independent marketing promotion where the business invests in `TV`, `Social_Media`, and `Radio` promotions to increase `Sales`.

The business would like to determine which feature most strongly predicts `Sales` so they have a better understanding of what promotions they should invest in in the future. To accomplish this, you'll construct a simple linear regression model that predicts sales using a single independent variable. 

# EDA & data cleaning
Some reasons for conducting EDA before conducting a simple linear regression model:
* Understanding which variables are present in the data
* Reviewing the distribution of features, such as minimum, mean, and maximum values
* Plotting the relationship between the independent and dependent variables to visualize which feature is the best choice for X
* Identifying issues with the data, such as incorrect values (e.g., typos) or missing values

Before fitting the model, ensure the Sales for each promotion (i.e., row) is present. If the Sales in a row is missing, that row isn't of much value to the simple linear regression model.   

# Model building  
Create a pairplot to visualize the relationships between pairs of variables in the data. You will use this to visually determine which variable has the strongest linear relationship with `Sales`. This will help you select the X variable for the simple linear regression.   

