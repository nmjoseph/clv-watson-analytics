# Customer Lifetime Value Prediction
Using Watson Analytics, you can predict behavior to retain your customers. You can analyze all relevant customer data and develop focused customer retention programs.

## Data Source
https://www.ibm.com/communities/analytics/watson-analytics-blog/marketing-customer-value-analysis/

There are 24 columns in the dataset, and the response variable is Customer Lifetime Value (CLV). The goal of this project is to identify the significant predictor variables from the other 23 columns and choose a model which best predicts a Customer's Lifetime Value from these variables. 

## Project Outline

#### Identify Significant Categorical Variables
Since most of the columns are categorical (State, Coverage, Education, Employment Status, Gender, Location Code, Marital Status, Number of Open Policies, Number of Policies, Policy Type, Policy, Renew Offer Type, Sales Channel, Vehicle Class, and Vehicle), then we first create barplots for each categorical variable against Customer Lifetime Value to observe any differences in the sub-categories of these variables. For categories with visual significant differences, we will run t-tests and ANOVA tests for the sub-categories to observe whether there is a significant difference in the mean Customer Lifetime Values between these groups. Any variables that output a p-value less that 0.05 indicate that there is a significant difference and these variables will be included in the model. Because some of the variables are right-skewed, then we will also create box plots to observe the distributions of the sub-groups. Groups with signficant differences in median and quartile values provides more evidence toward signficant differences in CLV with changes in the categorical variable.
