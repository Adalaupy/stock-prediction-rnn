## Table of contents
* [General Information](#general-information)
* [Functions](#functions)
* [Installation](#installation)

# General Information
This project uses a Recurrent Neural Network (RNN) built with Keras to predict stock prices.
It takes historical price data (such as open, high, low, close, volume) as input and trains the model to forecast future closing prices. The goal is to capture time-series patterns and trends in stock movements using deep learning.


# Functions
## 1. Hyperparameter & Input Feature Experiments *[main_RNN_Analysis.ipynb]*

Different stocks show unique patterns, so the optimal settings vary. We test combinations of key parameters to find the best setup for each stock.

### Parameters Tested
* Sequence length (lookback window)
* Prediction horizon (days ahead)
* Number of LSTM layers
* Data length (total historical days used)
* Training data fraction

### Flexible Grid Search
We use nested loops to try different combinations. The user can control the search space in two ways:

1. Define min / max / step
   Example: sequence length from 10 to 90, step = 10
   → automatically generates 10, 20, 30, ..., 90
2. Directly set total number of values
   Example: want exactly 5 different sequence lengths
   → code evenly distributes values between min and max

### Users can freely choose:
* Which parameters to tune
* Minimum and maximum value for each
* Step size (incremental) or total number of groups/values


## 2. Input Target Horizon *[main_RNN_Train.ipynb]*
After identifying the best combination of input variables (sequence length, features, layers, etc.) from the hyperparameter experiments, the user can specify the target prediction horizon (number of days ahead to forecast).

## 3. Predict Stock Price for Future Days *[main_RNN_Predict.ipynb]*
After training the model with the optimal parameters and chosen target horizon (from step 2), the model is ready to generate predictions.


# Installation
```
pip install -r requirements.txt
```
 



