# Damani Walker

## Machine Learning Signal Projector

## What is this?

The goal of this Project is to give investors clear signals on when to buy/sell stocks using machine learning models.
* Originally, a Monte Carlo simulation was going to be used in order to determine when the best time in the future to buy/sell stocks

Instead, we took the current return at a specific point in time and shifted it back 30 days to see if machine learning models could predict future returns

### Data and Model Training

- Data is gathered from historical csv’s
- We calculate the returns for the stock to see the general trajectory.

![alt text](https://github.com/DamaniW/Project_2/blob/main/TSLA_returns.png?raw=true)

Added a column for “Future Close” which takes the closing price 30 days after the first and sets it to the beginning.

Then added the “Short” and “Long” columns to serve as a feature for the upcoming signal
* Used a short window of 10
* Used a long window of 95

With this information, we can create our “Signal” column to determine when to buy/sell
* Buy if Signal = 1
* Sell iff Signal = -1
By using the diff() function we can visualize our entry/exit

![alt text](https://github.com/DamaniW/Project_2/blob/main/TSLA_signals.PNG?raw=true)

### Model Evaluation & Discussion

Originally, a Support Vector Machine (SVM) Classifier was used:

![alt text](https://github.com/DamaniW/Project_2/blob/main/TSLA_model_report.png?raw=true)

However, as you can see from the results, it did not perform very well. The precision and recall were completely different in from the training data to the testing data.

This could most likely be due to the fact that there wasn’t enough data to support the model.

In the future, a different model will be used, such as an oversampling model or a balanced random forest model
