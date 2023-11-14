# Alphabet Soup Neural Network Model Report

This project aims to create a deep learning model for Alphabet Soup. It is intended to predict the success of funding applicants based on the various features provided by the dataset. This report is based on the final optimized version of the model.

## Data Preprocessing

### Target Variable
- `IS_SUCCESSFUL`

### Feature Variables
- `NAME`
- `APPLICATION_TYPE`
- `AFFILIATION`
- `CLASSIFICATION`
- `USE_CASE`
- `ORGANIZATION`
- `STATUS`
- `INCOME_AMT`
- `SPECIAL_CONSIDERATIONS`
- `ASK_AMT`

### Removed Variables
- `EIN`
    - This column is purely used for identification, and has no relation to the success of a venture

## Compiling, Training, and Evaluation

### Neural Network Architecture
- A neural network with two hidden layers was created
    - First Layer
        - 80 neurons
        - ReLU activation
    - Second Layer
        - 30 neurons
        - ReLU Activation
    - Output Layer
        - Sigmoid Activation

### Model Optimization
The first trial of this model has an accuracy of 72.80%. The goal was to reach an accuracy of 75%, so the following optimization methods were used:
- Modifying feature variables and removed variables
    - This seems to have had the largest impact on the accuracy of each iteration of the model. While `NAME` was initially dropped, adding it back in increased performance significantly
- Increasing the amount of hidden layers
    - A third hidden layer was added to one of the model iterations, but was eventually removed due to lack of significant impact
- Modified bins
    - Changed the bins for `APPLICATION_TYPE` and `CLASSIFICATION` to decrease the amount of data being consolidated into one singular 'other' category
    - Reverted this change due to lack of positive impact

### Model Performance and Summary
After several optimization methods were tested, the model was able to achieve an accuracy of 96.83%, which far exceeds the inital goal of 75%. 

### Other Options
While this model is already performing well, it could be further improved by implementing hyperparameter tuning or using a Random Forest Classifier. Random Forests are less prone to overfitting and allow us to view feature importance.