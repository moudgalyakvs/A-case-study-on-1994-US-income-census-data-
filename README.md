# A-case-study-on-1994-US-income-census-data-
## Table of Contents
* [Introduction](#section-1)
* [Importing necessary libraries and packages](#section-2)
* [Understanding the data](#section-3)
    - [Importing the dataset](#subsect-1)
    - [Preliminary Analysis](#subsect-2) 
    - [Understanding categorical variables](#subsect-3)  
* [Exploratory data analysis](#section-4)    
    - [Analysis of the effect of different variables on 'target' variable](#subsect-4) 
    - [Splitting the dataframe with respect to capital transactions and analysing](#subsect-5)
    - [Correlation Analysis](#subsect-6)
* [Building the ML model on zero_cap_df [for those with zero capital transactions]](#section-5)
    - [Model building with Recursive Feature Elimination](#subsect-7)   
    - [Random forest with RFE](#subsect-8) 
    - [Model building with Principal Component Analysis (PCA)](#subsect-9)  
    - [Random forest with PCA](#subsect-10)
    - [Gradient boosting method with RFE](#subsect-11)
* [Building the ML model on gain_loss_cap_df [for those with some significant capital transactions]](#section-6)
    - [Random forest with RFE](#subsect-12) 
* [Conclusions](#section-7)

<a id="section-1"></a>
# Introduction

#### About the dataset
The dataset has been taken from the famous UCI Machine Learning Repository. Extraction was done by Barry Becker from the 1994 Census database. The dataset is set for a prediction task to determine whether a person makes over $50,000/year.
#### Business objective
* To understand and arrive at some interesting insights related to income of an individual from the individual's work, education and personal details

* To buid a predictive model to serve two main purposes:
>* To predict whether an individual falls to an annual income category of above $50,000, with known information such as age, workclass, education, etc.
>* To identify the important variables that strongly influence the prediction
##### Procedure
* First objective can be extracted by data visualization achieved through exploratory data analysis
* Second objective is achieved by building various machine learning models optimized for better results

#### Expected Outcomes from the business objectives
* Based on the income category an individual falls into and understanding the income pattern of certain groups, goa targeted marketing campaigns can be carried out to reach out to such groups and hence individuals.

* By knowing the features that influence the high income of an individual, companies and governments get an estimate so as to understand to which income slab does an employee fit into.

##### Attribute Information

* 'target' variable: to classify the income of individual into >$50K or <=$50K category.

>* age: continuous.
>* workclass: Private, Self-emp-not-inc, Self-emp-inc, Federal-gov, Local-gov, State-gov, Without-pay, Never-worked.
>* fnlwgt: continuous.
>* education: Bachelors, Some-college, 11th, HS-grad, Prof-school, Assoc-acdm, Assoc-voc, 9th, 7th-8th, 12th, Masters, 1st-4th, 10th, Doctorate, 5th-6th, Preschool.
>* education-num: continuous.
>* marital-status: Married-civ-spouse, Divorced, Never-married, Separated, Widowed, Married-spouse-absent, Married-AF-spouse.
>* occupation: Tech-support, Craft-repair, Other-service, Sales, Exec-managerial, Prof-specialty, Handlers-cleaners, Machine-op-inspct, Adm-clerical, Farming-fishing, Transport-moving, Priv-house-serv, Protective-serv, Armed-Forces.
>* relationship: Wife, Own-child, Husband, Not-in-family, Other-relative, Unmarried.
>* race: White, Asian-Pac-Islander, Amer-Indian-Eskimo, Other, Black.
>* sex: Female, Male.
>* capital-gain: continuous.
>* capital-loss: continuous.
>* hours-per-week: continuous.
>* native-country: United-States, Cambodia, England, Puerto-Rico, Canada, Germany, Outlying-US(Guam-USVI-etc), India, Japan, Greece, South, China, Cuba, Iran, Honduras, Philippines, Italy, Poland, Jamaica, Vietnam, Mexico, Portugal, Ireland, France, Dominican-Republic, Laos, Ecuador, Taiwan, Haiti, Columbia, Hungary, Guatemala, Nicaragua, Scotland, Thailand, Yugoslavia, El-Salvador, Trinadad&Tobago, Peru, Hong, Holand-Netherlands.
