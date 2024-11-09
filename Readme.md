**Data Preprocessing and Feature Engineering**

1. First we dropped off the null values and those values which were way too large compared to the other values of the .  
2. Then, we removed those values in which Volume was 0 but still there was a change in price which is not possible since trading didn’t happen on that day.  
3. As the next step, we removed those datapoints where there is a price change of more than 25% in a day (considering that no company grows or drops 25% in a day).  
4. We created new variables, viz, Moving Average-20(to smoothen out the price change), RSI(Relative Strength Index), STD20(to predict a deviation in the prices). Then classified the price fluctuations into Bullish Divergence, Bearish Divergence, Sharp RSI Change, Normal and Anomaly.  
5. Now, we found out the Bollinder Band of the prices(window \= 20).  
   

**Training the Model**

1. We decided to train the model using DL techniques given the data was considerably large and the decision to be made among the variables was slightly complicated.  
2. Employed Sequential Neural Network to fit the model on the featured dataset.  
3. The logic is \- if the given price doesn’t satisfy the Bollinger curve then it is considered as an Anomaly.  
4. Optimiser \- Adam

	Loss \- MSE  
	No. of dense layers \= 3(tried with 2,3,4 and 5 but 3 yielded the best result)  
	Loss after training \= 0.0035

**Failed Attempts**

* We tried employing ARIMA and SARIMA techniques but it didn’t yield desired results.  
* Tried incorporating MACD and CAPM trading strategies but they didn’t sit well with predicting anomalies rather they are used for predicting gains and losses.  
* Created a model using LSTM on the aforementioned features but the closing\_price v/s predicted price hardly yielded any anomalies.

