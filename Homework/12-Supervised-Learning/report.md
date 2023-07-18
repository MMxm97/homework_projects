# Module 12 Report Template

## Overview of the Analysis

Based on the provided dataset of historical lending activity with such data as loan size, interest rate, borrowers income, debt-to-income ratio, number of account, derogatory marks, total debt, and loan status the purpose of the assignment analysis was to build, train, test and evaluate the models to predict the loan status `0` (healthy loan) vs `1` (high-risk loan). 

Those were two logistic regression models. For the first one the original dataset, fit with inbalanced data where healthy loans outnumbering high-risk ones, was used. For the second model the data were resampled by using the `RandomOverSampler` module from the imbalanced-learn library.

For both models, the count of the target classes was derived,  a logistic regression classifier trained,  the balanced accuracy score calculated, a confusion matrix and a classification report generated.

The analysis included the following stages of the machine learning process:

- splitting the original data into training and testing sets,
- creating and fitting a logistic regression model with the original data,
- evaluating the model’s performance by generating and looking at the accuracy, precision and recall scores of the model,
- using the `RandomOverSampler` module from the imbalanced-learn library to resample the data to have the equal number of `0` (healthy loans) and `1` (high-risk loans) as the loan status,
- fitting the model with the resampled data to make predictions using the `LogisticRegression` classifier, 
- evaluating the resampled data model’s performance by generating and looking at the accuracy, precision and recall scores of the model.
 
 

  

## Results

Machine Learning Model 1 (the logistic regression, fit with imbalanced / original data):

-  The accuracy score is equal to 95 % which is pretty high meaning that approximately 95% of the loans in the test data were accurately categorized by the model. However, based on value_counts, there were very few loans in the data that were actually high-risk loans, and so the model could have had high accuracy by simply predicting all loans to be healthy.

-  The precision score for `0` (healthy loan) is 1 or 100%.  It means that there are no false positives but only the true positives. 85% precision for '1' looks good although not perfect 100% and implies some false positives in predicting high-risk loans.

-  The recall score for '0' (healthy loan) is equal to 99%. This means that the model predicts the healthy loans well with almost no false negatives. It is 91% for the high-risk loans which is pretty high, although not perfect, bearing some false negatives. 



Machine Learning Model 2 (the logistic regression, fit with resampled data):
  
-  The accuracy score is over 99 % which is almost perfect meaning that over 99% of the loans in the test data were accurately categorized by the model.

-  The precision score for `0` (healthy loan) is 1 or 100%.  It means that there are no false positives but only the true positives. 84% precision for '1' looks good although not perfect 100%, yet 1% lower than in the imbalanced data case. It implies some false positives in predicting high-risk loans.

-  The recall score for '0' (healthy loan) is equal to 99%. This means that the model predicts the healthy loans with almost no false negatives. It is 91% for the high-risk loans which is pretty high, although not perfect, bearing some false negatives. 
  

## Summary

In overall, the 2nd logistic regression model, fit with resampled (balanced) data, seems to perform better considering 4% better accuracy and 8% better precision in predicting high-risk loans.  These score increases outweigh the model's 1% decrease of the precision score for the high-risk loans meaning 1% more false positives vs 8% less false negatives. Yet, a false positive is an error in which a test result incorrectly indicates the presence of a condition, here, high-risk loan. It means that the second model is somewhat more conservative and / or "overcautious' in detecting bad loans which one may consider as a barrier in preventing losses through disbursing high risk loans. 
