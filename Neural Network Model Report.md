# Neural Network Model Report

## Overview
- The purpose of this exercise is to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.
- Alphabet Soup’s business team has provided a CSV containing more than 34,000 organizations that have received funding  over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

  - **EIN** and **NAME**—Identification columns
  - **APPLICATION_TYPE**—Alphabet Soup application type
  - **AFFILIATION**—Affiliated sector of industry
  - **CLASSIFICATION**—Government organization classification
  - **USE_CASE**—Use case for funding
  - **ORGANIZATION**—Organization type
  - **STATUS**—Active status
  - **INCOME_AMT**—Income classification
  - **SPECIAL_CONSIDERATIONS**—Special considerations for application
  - **ASK_AMT**—Funding amount requested
  - **IS_SUCCESSFUL**—Was the money used effectively

- We used the `Sequential` from `Keras` to create the Neural Network Model and in order to achieve the highest accuracy we used Keras Tuner.

## Results

- Data Prepocessing
    - What variable(s) are the target(s) for your model?
        - The target variable is the **IS_SUCCESSFUL** column
    - What variable(s) are the features for your model?
        - **EIN** and **NAME**
        - **APPLICATION_TYPE**
        - **AFFILIATION**
        - **CLASSIFICATION**
        - **USE_CASE**
        - **ORGANIZATION**
        - **STATUS**
        - **INCOME_AMT**
        - **SPECIAL_CONSIDERATIONS**
        - **ASK_AMT**
        - **IS_SUCCESSFUL**
    - What variable(s) should be removed from the input data because they are neither targets nor features?
        - The columns `EIN` and `NAME` were dropped since they don't affect the model outcome

- Compiling, Training, and Evaluating the Model
    - How many neurons, layers, and activation functions did you select for your neural network model, and why?
        - The very first attempt before any optimization was done, had many hidden layers in order to create a complex model and hoping to achieve high accuracy
    - Were you able to achieve the target model performance? NO
    - What steps did you take in your attempts to increase model performance?
        - After a very low accuracy and high loss, I decided to decrease the number of hidden layers to only three and changed the activation function to `sigmoid` for the output layer.

## Summary

We were tasked with developing a deep learning neural network model for the client AlphabetSoup. The purpose of the model is to select the applicants that have the highest change of success and in hopes of allocating funding better. 
The first part of creating the model is preprocessing the data. During this step irrelevant identification columns were dropped. After, binning was done to simplify data and identify patterns. Then, dummying categorical columns, and finally scaling the training and testing features datasets for a more effective model training.
I used a Keras Tuner hyperparameter. Then compiled, trained, and evaluated the best-tuned model with the neural network. It had multiple hidden layers but gave a dissappointing 49% accuracy and even greater loss.
During the optimization, I changed the activation fuctions and decreased the numbers of hidden layers in order to decrease the loss of the model and increase the accuracy. After three atempts the target 75% accuracy was not achieved. The results are as follows:


<img width="138" alt="AnalysisTable" src="https://github.com/mariadiosdado/deep-learning-challenge/assets/136658866/ee50443d-8e32-4252-9423-14ae3c934e9f">

Another method that can be used is logistic regression. It is easy to use when dealing with binary classification problems but it works better for smaller datasets. Another model to try in order to increase accuracy is decision Trees. This model is also easy to interpret and does not require too much data cleaning but it can be prone to overfitting. 

