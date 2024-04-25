# Alphabet Soup Training Analysis

## Overview

### Goal: Create a model to predict whether an application will be successful if funded by Alphabet Soup

Predict a binary classification using different attributes of applicants.

## Results

### Data Preprocessing

Target Variable: "IS_SUCCESSFUL" Binary classification

Features: Application Type, Affiliation (Sector), Classification (Government), Use Case, Organization Structure Type, Binary Active Status, Income Range, Binary Special Considerations, Ammount Reuqested

Dropped Name and EIN, nothing to gain

### Inital Model

- First Hidden Layer: 80 neurons, relu activation, input dim 44 (44 features)

- Second Hidden Layer: 30 neurons, relu activation

- Output Layer: sigmoid activation for binary classification.

- Loss (binary cross entropy): 0.556

- Accuracy: 0.73

- Not able to hit 0.75% Accuracy goal.

### Optimizations

1. Add ASK_INCOME Binary Feature

    Is the funding requested within the Income Range for the applicant?

    Compare Ask Amount to the Max of the Income Classification.

    if Max > Ask Amount: True
    if Max < Ask Amount: False

2. Add Layers to NN

    Increase Dense layers to 5, neurons to 128

    Add L2 Regularization and Dropout Layers

3. Decrease lower cutoff for binning

    Classification to 50

    Application type to 100

## Summary

The optimizations made to the in initial model did not increase it's accuracy. I would recommend using a non-neural network model such as a Binary Logistic Regression, as it would be less prone to overfitting while delivering similar results in a more customizable model.










