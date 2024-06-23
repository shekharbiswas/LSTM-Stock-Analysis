# Key Hyperparameters in LSTM

## Number of LSTM Units:

- The number of memory cells in each LSTM layer.
- Controls the capacity of the model to learn temporal dependencies.
- Common values: 50, 100, 150.


## Number of LSTM Layers:

- The number of stacked LSTM layers in the network.
- Adding layers can allow the model to learn more complex patterns.
- Common values: 1, 2, 3.

## Dropout Rate:

- The fraction of input units to drop during training.
- Helps to prevent overfitting by making the model more robust.
- Common values: 0.2, 0.3, 0.4, 0.5.

## Learning Rate:

The step size used by the optimizer to update the weights.
Affects the speed and quality of the learning process.
Common values: 0.001, 0.01, 0.1.
Batch Size:

The number of training examples used in one iteration of model training.
Larger batches can improve gradient estimates but require more memory.
Common values: 32, 64, 128.
Number of Epochs:

The number of complete passes through the training dataset.
More epochs allow the model to learn longer but risk overfitting.
Common values: 10, 20, 30.
Optimizer:

The algorithm used to minimize the loss function.
Common choices include Adam, RMSprop, and SGD.
Hyperparameter Tuning Techniques
Grid Search:

Exhaustively searches through a predefined set of hyperparameters.
Suitable for smaller search spaces.
Time-consuming but simple to implement.
Random Search:

Samples hyperparameters randomly from a defined range.
Often more efficient than grid search as it explores more diverse values.
Can find good configurations faster.
Bayesian Optimization:

Uses probabilistic models to identify promising hyperparameters.
Efficient for complex and high-dimensional search spaces.
Balances exploration and exploitation to find optimal values.
Process of Hyperparameter Tuning
Data Preparation:

Normalize and preprocess the historical stock price data.
Create sequences suitable for LSTM input.
Model Definition:

Define the LSTM model architecture with tunable hyperparameters.
Cross-Validation:

Split the data into training and validation sets to evaluate model performance.
Use cross-validation to ensure the model generalizes well to unseen data.
Search for Optimal Hyperparameters:

Apply grid search, random search, or Bayesian optimization to find the best hyperparameters.
Train multiple models with different hyperparameter combinations.
Model Evaluation:

Assess the performance of each model using metrics like Mean Squared Error (MSE) or Mean Absolute Error (MAE).
Select the model with the best validation performance.
Testing:

Evaluate the best model on a separate test set to ensure it performs well on unseen data.
