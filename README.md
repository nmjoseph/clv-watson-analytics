# Customer Lifetime Value Prediction
Using Watson Analytics, you can predict behavior to retain your customers. You can analyze all relevant customer data and develop focused customer retention programs.

## Data Source
https://www.ibm.com/communities/analytics/watson-analytics-blog/marketing-customer-value-analysis/

There are 24 columns in the dataset, and the response variable is Customer Lifetime Value (CLV). The goal of this project is to identify the significant predictor variables from the other 23 columns and choose a model which best predicts a Customer's Lifetime Value from these variables. 

## Project Outline

#### Identify Significant Categorical Variables
Since most of the columns are categorical (State, Coverage, Education, Employment Status, Gender, Location Code, Marital Status, Number of Open Policies, Number of Policies, Policy Type, Policy, Renew Offer Type, Sales Channel, Vehicle Class, and Vehicle), then we first create barplots for each categorical variable against Customer Lifetime Value to observe any differences in the sub-categories of these variables. For categories with visual significant differences, we will run t-tests and ANOVA tests for the sub-categories to observe whether there is a significant difference in the mean Customer Lifetime Values between these groups. Any variables that output a p-value less that 0.05 indicate that there is a significant difference and these variables will be included in the model. Because some of the variables are right-skewed, then we will also create box plots to observe the distributions of the sub-groups. Groups with signficant differences in median and quartile values provides more evidence toward signficant differences in CLV with changes in the categorical variable.

#### Identify Significant Numerical Variables
Remaining columns with continuous numerical values include Income, Monthly Premium Auto, Months Since Last Claim, Months Since Policy Inception, Number of Open Complaints, Number of Open Policies, and Total Claim Amount. Because Number of Open Complaints and Number of Open Policies are not continuous variables, we will treat them as categorical. The same process as above will be done to observe which variables have a strong correlation to CLV. To identify relationships between the other predictors with Customer Lifetime Value, we create scatterplots of the data to observe an visual relationship. Variables with small p-values from the ANOVA test and an relationship CLV will be added to the model.

#### Identify Possible Time Dependence
One variable 'Effective to Date' might be heavily correlated with Customer Lifetime Value. Since it is related to time, this could be evidence of time dependence that could skew the results. In order to identify this possible model assumption violation, we will conduct a runs test. A p-value less than 0.05 shows that there is evidence of time dependence in the data. If this is present, then we will need to consider transformations to the response variable to eliminate this dependence.

#### Models
* Multiple Linear Regression
* Multiple Linear Regression with Log Transformation of CLV
* Polynomial Model of Degree 2 with Log Transformation of CLV

#### Checking for Overfitting/Underfitting
We use compare the training and testing set scores (MSE and MAPE) to check whether the model fits the training set perfectly or not at all. Then we use cross validation with ten subsets of the data in order to observe whether some sets are fitted well to the data and some are not. If the scores are around the same for each subset, then there are no signs of over or under-fitting.
