# MicrosoftStockSupML
Supervised Machine Learning Project for Microsoft Stock Prices from 2000 - 2023
# DTSA 5509 - Supervised Machine Learning - Final Project: Microsoft Stock Prices From 2000 - 2023.

The following dataset is from Kaggle (https://www.kaggle.com/datasets/prajwaldongre/microsoft-stock-price2000-2023/data) and represents the Microsoft Stock Price form 2000 - 2023. The data is split into the following columns (copied directly from Kaggle):

* Date: This column represents the calendar date when the data about the stock is recorded.

* Open: This column represents the first recorded price of the stock for a trading session.

* High: The high price represents the highest traded price of the stock during a given trading session. It reflects the peak value that the stock reached during the day.

* Low: The low price is the lowest traded price of the stock during a specific trading session. It indicates the minimum value that the stock reached during the day.

* Close: The closing price is the last traded price of the stock at the end of a trading session. It reflects the final value at which the stock was traded before the market closes.

* Adj Close(Adjusted Close): The adjusted closing price accounts for corporate actions, such as dividends, stock splits, and new stock offerings, that may affect the stock's price but are not directly related to its performance. The adjusted close is often used to assess the stock's performance over time.

* Volume: Volume represents the total number of shares traded during a specific time period. It gives an indication of the level of market activity and liquidity for that stock. High volume often suggests increased investor interest, while low volume may indicate less active trading.

This project is to examine how Supervised Machine Learning Models can help predict beneficial information to an investor in Microsoft Stock by examining how to predict closing prices and positive/negative returns. 

## First Supervised Machine Learning Problem: Can we predict the closing price based on Linear Regression models?

The first model looks at predicting the closing price via a Linear Regression Model. From the EDA performed previously, there are a lot of columns that have signifcant correlation. The first section of models all represent linear regression models with different features utilized for predicting the closing price. The model first utilized features from all of the given columns (excluding 'Returns' which was later added). The second model then utilizes just the 'Open' price to predict the 'Close' price. The last model then utilizes just the 'Volume' to redict the 'Close' price. The first two models were selected to see how accurate the linear regression model is utilizing information that should obviously yield closing prices (based on correlation from EDA and the fact that the opening prices do not sway significantly day to day from the closing prices). The last model aims to predict the 'Close' price based on Volumes, which does not have high correlation, and would be less obvious as a predictor.

## Second Supervised Machine Learning Problem: Can we predict a positive or negative return based on classification models? 

The next section examines the possibility of predicting a positive or negative return using various classification, supervised, machine learning models. The 'Returns' column was previously created, and represents a binary datatype that indicates whether a closing price will increase (1) or decrease (0) in the next time step. Four different classification models were developed to compare the results. The four different classification models utilized:

* Logistic Regression Model
* Support Vector Machine (SVM) Model
* Random Forest Model
* K-Nearest Neighbors (KNN) Model

The models were developed below, and the accuracy, confusion matrix, classification report, and Receiver Operating Characteristic Curve (ROC) with Area Under the Curve (AUC) were provided for each of the models. Being able to predict whether the Microsoft Stock has a positive or negative return can provide investors with a significant advantage in choosing when to invest.

### Conclusion

This project looks at how we can predict closing prices and positive/negative returns from the Microsoft Stock Data via supervised machine learning models such that investors have a leg-up on investing. The closing prices were predicted via three linear regression models:

* Predicting 'Close' via all given features ('Open', 'High', 'Low', 'Volume', 'Adj Close')
* Predicting 'Close' via just one feature with high correlation ('Open')
* Predicting 'Close' via just one feature with low correlation ('Volume')

The first two linear regression models yielded very positive results with a near R-squared value of 1.0 and a Mean Squared Error (MSE) of less than 1 for the model utilizing all given features and approximately 3.2 for the model utilizing just 'Open'. These models should yield accurate results as the values of stock prices during closing should not fluctuate significantly from the opening stock prices. Additionally, factors like 'Adj. Close' and 'High' and 'Low' would also show very little fluctuation; therefore, the models are not extremely helpful. The third model looks at predicting 'Close' via the 'Volume' of stocks sold. This showed a minimal correlation in the EDA, and any model yielding accurate results would be extremely beneficial to the investor. The results; however, were not accurate, which is not surprising. The model itself yielded a Mean Squared Error of around 6400 and an R-squared of around 0.178.

The positive/negative returns were predicted using binary classification methods. All four models struggled to predict positive or negative returns accurately. The models utilized for this project are described below.


**The Logistic Regression Model:**

- Precision: For class 0, it's 0.53, and for class 1, it's 0.50. These values indicate the proportion of true positive predictions among all positive predictions.

- Recall (Sensitivity): For class 0, it's 0.26, and for class 1, it's 0.76. These values indicate the proportion of true positive predictions among all actual positive instances.

- F1-score: For class 0, it's 0.34, and for class 1, it's 0.60.

- Accuracy: 0.50, indicating that the model correctly predicts the target variable in 50% of the instances.


**The Support Vector Machine Model:**

- Precision: For class 0, it's 0.43, and for class 1, it's 0.48. These values indicate the proportion of true positive predictions among all positive predictions.

- Recall (Sensitivity): For class 0, it's 0.04, and for class 1, it's 0.95. These values indicate the proportion of true positive predictions among all actual positive instances.

- F1-score: For class 0, it's 0.07, and for class 1, it's 0.64.

- Accuracy: 0.48, indicating that the model correctly predicts the target variable in 48% of the instances.


**The Random Forest Model:**

- Precision: For class 0, it's 0.52, and for class 1, it's 0.50. These values indicate the proportion of true positive predictions among all positive predictions.

- Recall (Sensitivity): For class 0, it's 0.49, and for class 1, it's 0.52. These values indicate the proportion of true positive predictions among all actual positive instances.

- F1-score: For both class 0 and class 1 it's 0.51.

- Accuracy: 0.51, indicating that the model correctly predicts the target variable in 51% of the instances.


**The K-Nearest Neighbors (KNN) Model:**

- Precision: For class 0, it's 0.54, and for class 1, it's 0.52. These values indicate the proportion of true positive predictions among all positive predictions.

- Recall (Sensitivity): For class 0, it's 0.49, and for class 1, it's 0.57. These values indicate the proportion of true positive predictions among all actual positive instances.

- F1-score: For class 0, it's 0.51, and for class 1, it's 0.54.

- Accuracy: 0.53, indicating that the model correctly predicts the target variable in 53% of the instances.


The success of these models indicates the difficulty in adequately predicting stock prices. 
