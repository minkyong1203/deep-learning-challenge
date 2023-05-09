# deep-learning-challenge

## Overview of the analysis
The purpose of this analysis is to examine how we might build a deep learning model that can help a venture funding organization decide which company candidates would be successful, if funded. The model would be built off of data of companies funded in the past by the organization.

## Results

**Data Preprocessing**

*What variable(s) are the target(s) for your model?*
The target variable is the `IS_SUCCESSFUL` column which indicates if the funding money was used effectively. 

*What variable(s) are the features for your model?*
The feature variables are:
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special considerations for application
- ASK_AMT—Funding amount requested

*What variable(s) should be removed from the input data because they are neither targets nor features?*
Variables that should be removed are: EIN and NAME— Identification columns. These columns are only for identification purposes; adding them would only create noise in the model and are not factors that influence the success ooutcome of the company.

**Compiling, Training, and Evaluating the Model**

*How many neurons, layers, and activation functions did you select for your neural network model, and why?* 
One hidden layer was added to start, and for this, the ReLu function was used. ReLu was used because the dataset includes positive values and deals with non-linear data. The sigmoid function was used for the output layer because the goal is to correctly determine, based off of the input, whether the company was financially successful (1) or not (0). 

For the first hidden layer, 8 neurons were used. The general rule of thumb is to use a number that is between the size of the input layer and output layer. Also, the data set wasn't complex and large to warrant a higher number of neurons. As we see in the model performance,  8 neurons and one hidden layer was enough to achieve more than 75% accuracy.

*Were you able to achieve the target model performance?*
Yes, the target model performance was achieved with one hidden layer, 8 neurons, and 50 epochs. The accuracy started stabilizing after 7 epochs at 99.9% accuracy.

*What steps did you take in your attempts to increase model performance?*
To increase model performance, a few of the key model optimization methods were used:
- Adding another hidden layer with more neurons (5)
- Adding more epochs (increased to 100)

A small number of neurons was added to the second hidden layer, as the model was already achieving target performance. These optimization methods helped the model reach target performance more quickly - after four epochs.


## Summary

Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.

This deep learning model achieves high accuracy of with a loss: 6.182602373883128e-05, and accuracy: 1.0. This means it can successfully predict whether or not a company is successful/will use funding money effectively based on input data. 

A logistic regression could also accomplish this classification problem, because it is a rather simple, binary classification problem we are dealing with. Neural network models are good for complex decision problems, which is not the case with this problem. 
