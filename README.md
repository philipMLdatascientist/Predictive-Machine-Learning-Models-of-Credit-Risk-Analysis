# Predictive Machine Learning Models of Credit Risk Analysis

Link to Jupyter notebook below:

https://github.com/philipMLdatascientist/Predictive-Machine-Learning-Models-of-Credit-Risk-Analysis/blob/main/CreditRiskDataAnalysisMachineLearningModels.ipynb

## Context

Will the customer default on the loan?

## Data
For this project, I am given a dataset which contains 1,000 rows of credit data with 
15 attributes. One of these is the target variable (goodbad), which is binary for whether or not the 
loan was defaulted on. I will perform the exploratory data analysis and create 
statistical models to predict whether a customer is a “good” credit risk based on these attributes 
and sample data. 
A description of each of the 15 columns is shown below. The “DM” you see in 
some of the variable descriptions stands for the Deutsche Mark, the German currency before 
switching to the Euro. 

## Data Description
Column 1: checking (categorical) 
Status of existing checking account (amount of money) 
A11 :      ... <    0 DM 
A12 : 0 <= ... <  200 DM 
A13 :      ... >= 200 DM  
A14 : no checking account 
 
Column 2: duration (numerical) 
        Duration of loan (in months) 
 
Column 3: credithistory (categorical) 
        Credit history 
        A30 : no credits taken/all credits paid back duly 
               A31 : all credits at this bank paid back duly 
        A32 : existing credits paid back duly till now 
              A33 : delay in paying off in the past 
        A34 : critical account/other credits existing (not at this bank) 
 
Column 4:  purpose (categorical) 
        Purpose of loan         
A40 : car (new) 
        A41 : car (used) 
        A42 : furniture/equipment 
        A43 : radio/television 
        A44 : domestic appliances 
        A45 : repairs 
        A46 : education         
A48 : retraining 
        A49 : business 
       A410 : other

Column 5: creditamount (numerical) 
        Credit amount 
 
Column 6: savings (categorical) 
        Savings account/bonds 
        A61 :          ... <  100 DM 
        A62 :   100 <= ... <  500 DM 
        A63 :   500 <= ... < 1000 DM 
        A64 :          .. >= 1000 DM 
               A65 :   unknown/ no savings account 
 
Column 7: employment (categorical) 
        Present employment since 
        A71 : unemployed 
        A72 :       ... < 1 year 
        A73 : 1  <= ... < 4 years   
        A74 : 4  <= ... < 7 years 
        A75 :       .. >= 7 years 
 
Column 8: installment (numerical) 
        Installment rate in percentage of disposable income 
 
Column 9: sex (categorical) 
        Personal status and sex 
        A91 : male   : divorced/separated 
        A92 : female : divorced/separated/married 
               A93 : male   : single 
        A94 : male   : married/widowed 
 
Column 10: debtors (categorical) 
        Other debtors / guarantors 
        A101 : none 
        A102 : co-applicant 
        A103 : guarantor 
 
Column 11: resident (numerical) 
        Years at current residence 
 
Column 12: age (numerical) 
        Age (in years) 
 
Column 13: housing (categorical) 
        Housing 
        A151 : rent 
        A152 : own 
        A153 : for free 
        
Column 14: existingcredits (numerical) 
               Number of existing credits at this bank 
 
Column 15: goodbad (target variable) 
  Whether or not loan is repaid 
  1: “good” – for good credit risk, loan is repaid 
  0: “bad” – for bad credit risk, loan is not repaid 
 

## Results Summary
### Logistic Regression Classification Report
            precision    recall  f1-score   support

           0       0.54      0.31      0.39        91
           1       0.75      0.89      0.81       209

    accuracy                           0.71       300

The logistic regression model yielded the lowest yet comparable accuracy score of 71% and has tied with others as the lowest performing predictive model. However, this is at a cut-off of 0.5. The optimal cutoff point for the logistic regression model is noted to be at 0.43, 0.44, and 0.47. These 3 threshold values produce the highest noted accuracy rate of 75.71%.
### Pruned Decision Tree Classification Report
              precision    recall  f1-score   support

           0       0.69      0.24      0.36        91
           1       0.74      0.95      0.83       209

    accuracy                           0.74       300
The pruned decision tree model yielded the second highest accuracy score of 74% and produced a very clear intuitive diagram of the decision rules and leaf nodes.
### GridSearch Decision Tree Classification Report
             precision    recall  f1-score   support

           0       0.62      0.11      0.19        91
           1       0.71      0.97      0.82       209

    accuracy                           0.71       300
Surprisingly, the GridSearch Decision Tree yielded the lowest accuracy score of 71% when compared to manually inputting hyperparameters sequentially. Nevertheless, the results are comparable and the process was much more efficient. Also, the results of using GridSeach to find the best hyperparameter changed every time due to the option of setting the 'splitter' hyperparameter to 'random'.
### Linear Support Vector Machine
              precision    recall  f1-score   support

           0       0.74      0.27      0.40        91
           1       0.75      0.96      0.84       209

    accuracy                           0.75       300
The linear support vector machine model - vs. RBF and Poly SVM - yielded a high accuracy score of 75%.
### RBF Support Vector Machine
              precision    recall  f1-score   support

           0       0.64      0.31      0.41        91
           1       0.75      0.92      0.83       209

    accuracy                           0.74       300
### Polynomial Support Vector Machine
              precision    recall  f1-score   support

           0       0.71      0.16      0.27        91
           1       0.73      0.97      0.83       209

    accuracy                           0.73       300
