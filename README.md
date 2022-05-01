# -RBCModule19-Challenge

## Overview of Project

This project is meant to exemplify preprocessing of data, and the modeling, training and testing of a neural network for classification of financial data into a binary category of "IS_SUCCESSFUL". The context is attempting to predict success of potential venture capital projects and which should be funded accordingly.

## Results

- Data Preprocessing
  - What variable(s) are considered the target(s) for your model?
    - Our target variable is "IS_SUCCESSFUL".
  
  - What variable(s) are considered to be the features for your model?
    - Our features are: "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT".

  - What variable(s) are neither targets nor features, and should be removed from the input data?
    - "NAME" and "EIN" are neither targets nor features.

- Compiling, Training, and Evaluating the Model
  - How many neurons, layers, and activation functions did you select for your neural network model, and why?
    - We made an initial guess on the number of neurons and layers, but during optimization, we ran a search for the best possible model. The search yielded a model with 'relu' activation functions and a structure as follows:

```
{'activation': 'relu',
 'first_units': 55,
 'num_layers': 5,
 'units_0': 20,
 'units_1': 15,
 'units_2': 15,
 'units_3': 10,
 'units_4': 25,
 'units_5': 20,
 'tuner/epochs': 3,
 'tuner/initial_epoch': 0,
 'tuner/bracket': 2,
 'tuner/round': 0}
 ```

  - Were you able to achieve the target model performance?
    - We were able to acheive the target performance of 75%.

  - What steps did you take to try and increase model performance?
    - In our preprocessing, we first reduced the number of unique values of our features by binning rare occurrences. Initially we did not bin the "ASK_AMT", however when optimizing the model we later took this measure. We convert categorical data to numerical, seperate it into training and testing data and scaled it. Tuning the binning and the neural network search were the biggest steps taken to increase the performance of the model.

## Summary

Overall our results are fairly successful at 75% accuracy however we would also recommend attempting a SVM (support vector machine) classification due to the ability of SVMs to interpret multiple data types and their success in binary classification problems.
