## Overview of the analysis

The purpose of this analysis is to create an algorithm to predict whether or not applicants to the non-profit foundation Alphabet Soup for funding will be successful or not. This will achieved by using the the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.

The CSV contains more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization.

This project includes a jupyter notebook file that builds, trains, tests and optimizes a deep neural network that models charity success from the features in a loan application data set. TensorFlow Keras Sequential model is employed with Dense hidden layers and a binary classification output layer and this model is optimized by varying the hyper parameters:

- Hidden layer activation functions
- Number of nuerons in first layer
- Number of hidden layers


## Data Preprocessing

- IS_SUCCESSFUL was considered and decided to be the target 
- application type, affiliation, classification, use case, oranganization, status, income amt, special considerations and ask amt were considered and decided to be the features
- EIN and NAME are neither targets or features and were removed


## Compiling, Training, and Evaluating the Model

- Basic Model:
    - Used sequential model with two layers with 80 and 30 nuerons respectively. Sigmoid activation function was employed for output layer and relu activation function was employed for the hidden layer.
    - with this model, accuracy of 73.1% was achieved and a loss of 56.9%
    - this model did not achieve the goal of accuracy higher higher than 75% 

- Improving Model:
    - In attempts to improve the model performance the Keras Tuner library was employed. The Keras Tuner is a library that helps you pick the optimal set of hyperparameters for your TensorFlow program. The process of selecting the right set of hyperparameters for your machine learning (ML) application is called hyperparameter tuning or hypertuning.
    - the model iterated over to find which activation function should be used in the hidden layer (choice between relu, tanh and sigmoid). tanh provided best results
    - the model also iterated to decide the number od nuerons in the first layer (between 1 and 80), 9 nuerons were picked
    - the model also iterated over to decide how many hidden layers and nuerons should layer have 
    - even with all these iterations the accuracy only went up to 73.5%. 


## Summary
The model still has room to improve, following things can be tested in a future iteration:
- reducing the number of features
- binning features in a different way
- changing the number of epochs
- testing different learning rates
- a different model like the random forest may also provide similar results and could be tested 

over all the nueral networks provides a 73% accuracy, which is below target but not too far off. 