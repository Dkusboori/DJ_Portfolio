# Earthquake Magnitude Prediction

## Overview

This project implements a hybrid neural network (HNN) model to predict earthquake magnitude based on seismic waveform features. The model uses a combination of support vector regression (SVR) and a neural network trained with enhanced particle swarm optimization (EPSO). 

The code performs the following steps:

1. Loads and preprocesses earthquake dataset with waveform features and magnitude labels.

2. Performs standardization on the input features. 

3. Tunes hyperparameters of an SVR model using grid search cross-validation.

4. Trains the best SVR model on the full training set.

5. Uses the SVR predictions as additional features for a neural network. 

6. Defines neural network architecture and bounds for EPSO.

7. Performs k-fold cross-validation to evaluate model performance.

8. For each fold:
   - Splits data into train/validation sets.
   - Standardizes features.
   - Trains SVR and makes predictions on validation set.
   - Feeds SVR predictions into neural network as extra features.
   - Trains neural network using EPSO.
   - Makes predictions and evaluates metrics on validation set.

9. Computes average evaluation metrics across all folds.

10. Visualizes model performance using plots:
    - Bar plot of metrics
    - Scatter plot of predictions vs actual 
    - Residual plot
    - Error distribution
    - CV performance

## Code Overview

The main functions and modules used:

- `train_test_split()`: Split data into train/test sets
- `StandardScaler()`: Standardize features
- `GridSearchCV()`: Tunes SVR hyperparameters
- `SVR()`: Support vector regression model
- `train_eps_ann()`: Train NN with EPSO 
- `predict_ann()`: Make predictions with NN
- `KFold()`: Create CV folds
- Evaluation metrics: `mean_squared_error`, `r2_score`, etc.
- `matplotlib`: Plotting model performance

The neural network is trained using a custom EPSO implementation to find optimal weights by minimizing the MSE objective.

## Usage

The code is structured into functions to allow modularization and re-use. To adapt the model to a new dataset:

1. Import and preprocess data into feature matrix `X` and labels `y`

2. Define `layer_sizes` and `bounds` for neural network 

3. Pass `X` and `y` to the cross-validation routine

4. The best SVR and NN will be trained on each fold and results aggregated

5. Model performance metrics and plots will be generated

The hyperparameters and model architecture can be customized as needed for a given problem. More details are provided in comments throughout the code.
