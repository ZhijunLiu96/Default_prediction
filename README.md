# A capstone project from Team B

## Feature selection
Our first step was running random forest and Adaboost through the entire dataset, choosing the top 150 features on each category, combining with lasso model L1 regularization to minimize the number of features. We considered each model as a weak learner and aggregated the result by majority vote. The result contained 2 features from applicants, 11 from the credit center, 71 from request info and 116 from 3rd party variable. We also added back age, gender, education level, and OS type which is recognized as non-significant in the model for further processing.

The next is the manual selection step. We drew the correlation matrix for each category of variables to 3rd pairs with a correlation greater than 0.8. We removed the one variable less correlated with bad30 within the highly correlated sets. We've been left with 150 features after this step.

Nevertheless,it may not be the most efficient model to include 150 features. Realizing this, we decided to use GBM and reduced the number of our features to 65.

## Models
XGboost, Logistic Regression with WOE, Easy Ensemble
