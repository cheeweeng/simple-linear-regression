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
![Image](https://github.com/user-attachments/assets/8d27a815-7b5b-4b6e-b0d7-249a0de197a8)

Before fitting the model, ensure the Sales for each promotion (i.e., row) is present. If the Sales in a row is missing, that row isn't of much value to the simple linear regression model.   
![Image](https://github.com/user-attachments/assets/f9010b37-3001-49ee-b633-acb2ac241cf4)  

![Image](https://github.com/user-attachments/assets/258ca31c-9272-47eb-9344-04729cd994cc)  

# Model building  
Create a pairplot to visualize the relationships between pairs of variables in the data. You will use this to visually determine which variable has the strongest linear relationship with `Sales`. This will help you select the X variable for the simple linear regression.   

![Image](https://github.com/user-attachments/assets/f09c8f52-4d41-4c80-99af-7c6f325a71d8)  
![Image](https://github.com/user-attachments/assets/f77f1ab0-ed12-4b99-95e4-b3a3c1b03137)  
From the pairplot viz, TV clearly shows the strongest linear relationship with Sales. Hence TV was slected as the x variable for the simple linear regression.  

# Build and fit the model  
The steps are:  
1. Define the ols formula
2. Create an OLS model using ols() function
3. Fit the model
4. save the result summary


![Image](https://github.com/user-attachments/assets/7667a4de-823d-4cdc-abee-0b19ac37e801)  
![Image](https://github.com/user-attachments/assets/66384b9a-8ff4-4aca-a9d4-293738313820)  

# Check model assumptions  
To justify using simple linear regression, check that the four linear regression assumptions are not violated. These assumptions are:

* Linearity
* Independent Observations
* Normality
* Homoscedasticity

# Linearity  
<p>The linearity assumption requires a linear relationship between the independent and dependent variables. Check this assumption by creating a scatterplot comparing the independent variable with the dependent variable.</p>

![Image](https://github.com/user-attachments/assets/291e3db1-3612-4c01-83cd-513a56a7032a)  
There is a clear linear relationship between TV & Sales, hence the linearity assumption is met.  

# Normality  
The normality assumption states that the errors are normally distributed.

Create two plots to check this assumption:

* **Plot 1**: Histogram of the residuals
* **Plot 2**: Q-Q plot of the residuals


![Image](https://github.com/user-attachments/assets/c0b35e99-0636-4944-a3b8-2dc25f7f6438)  
![Image](https://github.com/user-attachments/assets/9a909ed5-4cf3-410e-b3be-ecf4209ccfd6)

The histogram of the residuals are approximately normally distributed, which supports that the normality assumption is met for this model.The residuals in the Q-Q plot form a straight line, further supporting that the normality assumption is met.  

# Homoscedasticity  
The **homoscedasticity (constant variance) assumption** is that the residuals have a constant variance for all values of `X`.

Check that this assumption is not violated by creating a scatterplot with the fitted values and residuals. Add a line at $y = 0$ to visualize the variance of residuals above and below $y = 0$.  

![Image](https://github.com/user-attachments/assets/d8fd9df5-b84f-4eeb-8d3d-e3affaab4c4a)  
The variance of the residuals is consistant across all  𝑋. Thus, the assumption of homoscedasticity is met.  

# Results and evaluation  
![Image](https://github.com/user-attachments/assets/7cbf09aa-5c0c-4abe-a98e-b4c7a24a0fcc)   

## Interpret model results  
When TV is used as the independent variable, the coefficient of the intercept is -0.1263 and the slope is 3.5614.  
$Y = \text{Intercept} + \text{Slope} * X$

$\text{Sales (in millions)} = -0.1263 + 3.5614 * \text{TV (in millions)}$    

According to the model, when TV is used as the independent variable X, an increase of one million dollars for the TV promotional budget results in an estimated 3.5614 million dollars more in sales.  

## R-squared interpretation:  
Using `TV` as X results in a simple linear regression model with $R^{2} = 0.999$. In other words, `TV` explains $99.9\%$ of the variation in `Sales`.  
The linear regression model estimates that 99.9% of the variation in sales is explained by the TV promotional budget. In other words, nearly all of the variation in sales can be explained by the TV promotional budget alone, making TV an excellent predictor of sales. TV spending is a strong predictor of Sales
The R-squared value will depend on the variable selected for X.   

## Interpretation of interpretation of the p-value and confidence interval for the coefficient estimate of X  
![Image](https://github.com/user-attachments/assets/3aa0c9da-a142-4896-b707-7a3ced33fbe8)  

when TV is used as the independent variable, it has a p-value of 0.000 and 95% confidence interval between 3.558 and 3.565  
This means there is a 95% chance the interval [3.558,3.565] contains the true parameter value of the slope. These results indicate little uncertainty in the estimation of the slope of X. Therefore, the business can be confident in the impact TV has on Sales.

## Conclusion  
Of the three available promotion types (TV, radio, and social media), TV has the strongest positive linear relationship with sales. According to the model, an increase of one million dollars for the TV promotional budget will result in an estimated 3.5614 million dollars more in sales. This is a very confident estimate, as the p-value for this coefficient estimate is small. Thus, the business should prioritize increasing the TV promotional budget over the radio and social media promotional budgets to increase sales.  
