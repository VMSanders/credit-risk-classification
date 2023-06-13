# credit-risk-classification
GTPE Data Science Boot Camp Module 20 Challenge

This repository contains course-provided starter code, including lending_data.csv which was used as the base dataset, and a Jupyter notebook that analyzes the dataset.

Analysis Overview

The analysis was on loan data, and the original dataset contained the following columns:
  Loan size
  Interest rate
  Borrower's income
  Debt to income ratio
  Number of accounts
  Derogatory marks
  Total debt
  Loan status
  
Loan status was either healthy (0) or high risk (1), and functioned as the labels for the dataset. All other columns remained as features of the dataset. 
The dataset includes 75036 healthy loans and 2500 high risk loans.

The goal of the analysis was to train a model to be able to predict loan status for future loans not yet evaluated.

The dataset was split into training and testing sets and used to train a logistic regression model. 
This method was repeated with a random oversampling on the dataset to get equal numbers of healthy and high risk loans.

Results

Logistic Regression Model 1 with original dataset:
  Balanced accuracy score: 0.9442676901753825
                precision    recall  f1-score   support

           0       1.00      1.00      1.00     18759
           1       0.87      0.89      0.88       625

    accuracy                           0.99     19384
   macro avg       0.94      0.94      0.94     19384
weighted avg       0.99      0.99      0.99     19384

Logistic Regression Model 2 with oversampled data:
  Balanced accuracy score: 0.9945359560744176
                precision    recall  f1-score   support

           0       0.99      1.00      0.99     18759
           1       1.00      0.99      0.99     18759

    accuracy                           0.99     37518
   macro avg       0.99      0.99      0.99     37518
weighted avg       0.99      0.99      0.99     37518


Summary

Of these 2 models, I recommend using the second model with the resampled data. 
The oversampling helps to correct the issue where Model 1 struggled to identify high risk loans due to smaller training set size and it doesn't lose much precision on healthy loans either.
In this particular example, we only have 2 options of healthy loan or high risk. While I'm not a lender, I imagine that you would want to accurately predict healthy loan status and only approve loans in that case.
If I were a borrower, I would prefer to avoid being misclassified as a high risk.
