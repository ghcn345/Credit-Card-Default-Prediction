![CC](/images/CC.jpg)

# Credit Card Default Prediction

**Authors**: Ning Chen, Michael Pozenvasser

## Overview
This research aimed at the case of customers default payments and compares the predictive accuracy of probability of default. Dataset was constructed by both [API](https://www.fraudlabspro.com/developer) calls and kaggle dataset. The research is studied as a classification machine learning problem with a binary variable, default payment as the response variable, and 23 explanatory features as predictor variables.


## Business Understanding
Machine learning methods are extensively used in finance, banking and insurance. The features of default payments, demographic factors, credit data, history of payment, and bill statements of credit card clients are all important information for data scientists to predict the customers potential consumption and bank credit. From the perspective of risk management, the result of predictive accuracy of the estimated probability of default will be more valuable than the binary result of classification - credible or not credible clients. 


## Data Understanding

### Data Collection
In light of the finance problem we are interested in, related APIs are searched and compared to construct our dataset. Classical kaggle dataset and UCI machine learning repositroy in Center for Machine Learning and Intelligent Systems are referenced to our study.


### Exploratory Data Analysis (EDA)

Relationship between exploratory variables and target variable
![overall](/images/overall.jpg)

Statistics for categorical variables
![groupby](/images/groupby.jpg)

### Feature Engineering

By data preprocessing, domain-motivated features are developed. Positvely contributed features are tested to evaluate their performance in modeling. New features and interaction features such as delinquency, probability of default and exposure at default are studied.

![Figure](/images/deliquency.jpg)

![Figure](/images/utility.jpg)

## Modeling Fitting

Multiple models including logistic regression, KNN(k-nearest neighbors), decision tree, random forest, SVM(support vector machine) and gridsearch & XGboost are all tested and compared. Pipeline is used with GridSearch. SMOTE and ADASYN are implemented to deal with the imbalance problem. Pros and cons are discussed for different models.

![Figure](/images/tree.jpg)

## Modeling Evaluation
The metric of accuracy score, F1 score, classification_report, confusion_matrix, roc curve and auc score are all evaluated and provided.

![Figure](/images/roc.jpg)



## Conclusions

1. The feature SEX and EDUCATION have different probability of default payment, according to both the statistical test and model evaluation, which means male/famle and different education levels have strong effects to the results.
2. Both continuous variable and categorical variables play important roles in the modeling. Different models mark different strong predictors.
3. The credit card default payment problem have highly imbalaced data. Even the data is processed with SMOTE technique, some metrics still does not show satisfactory reuslts. Because the real probability of default is unknown, we may implement artificial neural network to accurately estimate the real probability of default.


## For More Information

Please review our full analysis in [our Jupyter Notebook](https://github.com/ghcn345/Credit-Card-Default-Prediction/blob/master/CCDefaultPrediction.ipynb) or our [presentation](https://github.com/ghcn345/Credit-Card-Default-Prediction/blob/master/CreditPP.pptx).

For any additional questions, please contact **Ning Chen—chen.ning345@gmail.com, Michael Pozenvasser**.

## Repository Structure

Description of the structure of the repository and its contents:

```
├── README                              <- The top-level README for reviewers of this project
├── CCDefaultPrediction                 <- Narrative documentation of analysis in Jupyter notebook
├── order                               <- Python file for API call in FraudLabsPro Python Library
├── Project_Presentation                <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code

```


## Annotation

Column names and descriptions for Credit Card Clients Dataset.

* **ID**: ID of each client
* **LIMIT_BAL**: Amount of given credit in NT dollars (includes individual and family/supplementary credit
* **SEX**: Gender (1=male, 2=female)
* **EDUCATION**: (1=graduate school, 2=university, 3=high school, 4=others, 5=unknown, 6=unknown)
* **MARRIAGE**: Marital status (1=married, 2=single, 3=others)
* **AGE**: Age in years
* **PAY_0**: Repayment status in September, 2005 (-1=pay duly, 1=payment delay for one month, 2=payment delay for two months, … 8=payment delay for eight months, 9=payment delay for nine months and above)
* **PAY_2**: Repayment status in August, 2005 (scale same as above)
* **PAY_3**: Repayment status in July, 2005 (scale same as above)
* **PAY_4**: Repayment status in June, 2005 (scale same as above)
* **PAY_5**: Repayment status in May, 2005 (scale same as above)
* **PAY_6**: Repayment status in April, 2005 (scale same as above)
* **BILL_AMT1**: Amount of bill statement in September, 2005 (NT dollar)
* **BILL_AMT2**: Amount of bill statement in August, 2005 (NT dollar)
* **BILL_AMT3**: Amount of bill statement in July, 2005 (NT dollar)
* **BILL_AMT4**: Amount of bill statement in June, 2005 (NT dollar)
* **BILL_AMT5**: Amount of bill statement in May, 2005 (NT dollar)
* **BILL_AMT6**: Amount of bill statement in April, 2005 (NT dollar)
* **PAY_AMT1**: Amount of previous payment in September, 2005 (NT dollar)
* **PAY_AMT2**: Amount of previous payment in August, 2005 (NT dollar)
* **PAY_AMT3**: Amount of previous payment in July, 2005 (NT dollar)
* **PAY_AMT4**: Amount of previous payment in June, 2005 (NT dollar)
* **PAY_AMT5**: Amount of previous payment in May, 2005 (NT dollar)
* **PAY_AMT6**: Amount of previous payment in April, 2005 (NT dollar)
* **default.payment.next.month**: Default payment (1=yes, 0=no)