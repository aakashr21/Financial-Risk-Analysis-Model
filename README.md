![image](https://github.com/aakashr21/Financial-Risk-Analysis-Model/assets/88080322/1bc4f766-766f-459d-8d5b-f7a0e2b84601)

# Financial Risk Analysis Model

This project aims to leverage Exploratory Data Analysis (EDA) and machine learning to conduct risk analysis for loan default prediction in the context of a consumer finance company. This analysis will assist the company in minimizing financial losses while ensuring that creditworthy applicants are not unfairly rejected.

## Tools Used
# Import libraries for data wrangling
import numpy as np
import pandas as pd

# Import libraries for data visualisation
import matplotlib.pyplot as plt
import seaborn as sns

# Import libraries for model building
RandomForestClassifier
accuracy_score 
precision_score
recall_score
f1_score,roc_auc_score
confusion_matrix
ConfusionMatrixDisplay

     
## Insights
## All the analysis
* most of the customers have taken cash loan
* customers who have taken cash loans are less likely to default

**CODE_GENDER**
* most of the loans have been taken by female
* default rate for females are just ~7% which is safer and lesser than male

**NAME_TYPE_SUITE**
* unacompanied people had tanke most of the loans and the default rate is ~8.5% which is still okay

**NAME_INCOME_TYPE**
* the safest segments are working, commercial associates and pensioners

**NAME_EDUCATION_TYPE**
* Higher education is the safest segment to give the loan with a default rate of less than 5%

**NAME_FAMILY_STATUS**
* Married people are safe to target, default rate is 8%

**NAME_HOUSING_TYPE**
* People having house/appartment are safe to give the loan with default rate of ~8%

**OCCUPATION_TYPE**
* Low-Skill Laboreres and drivers are highest defaulters
* Accountants are less defaulters
* Core staff, Managers and Laborers are safer to target with a default rate of <= 7.5 to 10%

**ORGANIZATION_TYPE**
* Transport type 3 highest defaulter
* Others, Business Entity Type 3, Self Employed are good to go with default rate around 10 %

## Univariate numeric variables analysis
* most of the loans were given for the goods price ranging between 0 to 1 ml
* most of the loans were given for the credit amount of 0 to 1 ml
* most of the customers are paying annuity of 0 to 50 K
* mostly the customers have income between 0 to 1 ml

## Bivariate analysis
* AMT_CREDIT and AMT_GOODS_PRICE are linearly corelated, if the AMT_CREDIT increases the defaulters are decreasing
* people having income less than or equals to 1 ml, are more like to take loans out of which who are taking loan of less than 1.5 million, coudl turn out to be defaulters. we can target income below 1 million and loan maount greater than 1.5 million
* people having children 1 to less than 5 are safer to give the loan
* People who can pay the annuity of 100K are more like to get the loan and that's upto less than 2ml (safer segment)

## Analysis on merged data
* for the repairing purpose customers had applied mostly prev. and the same puspose has most number of cancelations
* most of the app. which were prev. either canceled or refused 80-90% of them are repayer in the current data
* offers which were unused prev. now have maximum number of defaulters despite of having high income band customers

## Model Evaluation
Confusion Matrix
![image](https://github.com/aakashr21/Financial-Risk-Analysis-Model/assets/88080322/8f6c2076-0e28-49a1-bc86-c076311c9c77)

Accuracy: 0.950842
Precision: 0.973602
Recall: 0.444372
F1 score: 0.610225
ROC AUC: 0.721615

## Conclusion

**Bank should target the customers**
* having low income i.e. below 1 ml
* working in Others, Business Entity Type 3, Self Employed  org. type
* working as Accountants, Core staff, Managers and Laborers
* having house/appartment and are married and having children not more than 5
* Highly educated
* preferably female
* unacompanied people can be safer -  default rate is ~8.5%

**Amount segment recommended**
* the credit amount should not be more than 1 ml
* annuity can be made of 50K (depending on the eligibility)
* income bracket could be below 1 ml
* 80-90% of the customer who were prev. canceled/refused, are repayers. Bank can do the analysis and can consider to give loan to these segments

**Precautions**
* org. Transport type 3 should be avoided
* Low-Skill Laboreres and drivers  should be avoided
* offers prev. unused and high income customer should be avoided
