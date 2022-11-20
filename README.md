# Module_14_Challenge
## Machine Learning Trading Bot
![Screenshot_header](../Screenshots/Screenshot2.png)
## Background
For this Challenge, I've had to assume the role of a financial advisor at one of the top five financial advisory firms.This firm competes with the other major firms to manage and automatically trade assets in a highly dynamic environment. In recent years, your firm has heavily profited by using computer algorithms that can buy and sell faster than human traders.

The speed of these transactions gave this firm a competitive advantage early on. But, people still need to specifically program these systems, which limits their ability to adapt to new data. I have improved the existing algorithmic trading systems to maintain the firm’s competitive advantage in the market. I have enhanced the existing trading signals with machine learning algorithms that can adapt to new data.

- I have created a Jupyter notebook to impliment the algorithmic trading using machine learning to automate trade decisions.
- Optimised the trading algorithm
- And trined the machine learning model

I was then able to compare the performance to that of the base line model.

## Establishing the Baseline performance.
I imported and reviewed the Pandas DataFrame and reviewed the data.

![Screenshot3](../Screenshots/Screenshot3.png)
I then calculated Actual Returns and dropped nulls. From this I generated the trading signals using short and long window SMA values. I then used this to generate the sSignal column.

![Screenshot4](../Screenshots/Screenshot4.png)

The Signal was multiplied by the Actual Returns to calculate the Strategy Returns before producing the following plot.

![Screenshot5](../Screenshots/Screenshot5.png)

## Split the data into training and testing datasets.
I used the SMA _Fast and the SMA _Slow and the Signal as the target column for the output. I then ran the training model.

![Screenshot6](../Screenshots/Screenshot6.png)

The SVC classifier model from SKLearn's support vector machine (SVM) learning method was used to fit the training data and make predictions based on the testing data.
The svm_pred was for predictions and the svm_testing_report was produced.

![Screenshot7](../Screenshots/Screenshot7.png)

As can be seen from the above results, the accuracy is poor and we should be able to do better.

I then created a predictions DataFrame that contains columns for “Predicted” values, “Actual Returns”, and “Strategy Returns.
The following predictions_df DataFrame was produced;

![Screenshot8](../Screenshots/Screenshot8.png)

I then createe a cumulative return plot that shows the actual returns vs. the strategy returns. 

![Screenshot9](../Screenshots/Screenshot9.png)

##Tune the Baseline Trading Algorithm

The second machine learning model was ran using a new LogisticRegression classifier. I useed the original training data as the baseline model and fitted the new classifier. A predictions report was produced.

![Screenshot10](../Screenshots/Screenshot10.png)

From the above report, it appears that the origina SVC classifier model proved to be the slightly better model although still a poor accuracy in predicting the 'Sell' signals of -1.0.

I then made a predictions2_df DataFrame;

![Screenshot11](../Screenshots/Screenshot11.png)

The Actual Returns and the Strategy Returns were then plotted.

![Screenshot12](../Screenshots/Screenshot12.png)

As can be seen the Strategy returns were better than the Actual Returns which is usually the case due to a number of factors including market slippage, optimal entry and exit positions and systems lags may be the cause of some of the variance.