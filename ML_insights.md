# Insights on Our Machine Learning Models 
## Preprocessing 
First, we had to implement the countries to a higher level of categories (5 U.S Region). 
We also converted the categorical data (Airport, Airline, etc.) into dummy/indicator variables. 
We are dropping the same columns for every model because they overlap with our target variable (DELAYED). The columns that we are dropping are: 
* DATE 
* DEP_TIME
* DEP_DELAY_GROUP
* DEST_STATE_NM
* DEST
* DEP_DELAY
* LATE_AIRCRAFT_DELAY
* CARRIER_DELAY
* WEATHER_DELAY
* SECURITY_DELAY
* NAS_DELAY
* DELAY_REASON
* CRS_DEP_TIME

## Processing 
* _We separated the feature (x) from the target (y)_ : Our target is “delayed,” while the rest of the columns are our features that might influence the chances of a flight being delayed 
* _Training and Test_ : The y-test value in the logistic regression model has 222,493 on-time flights and 47,885 delayed flights.
* _Scaling_ : Since our X values feature different values, we want to avoid large numbers that can disproportionately impact the model.

### Logistic Regression ###
* Accuracy 
  * The accuracy score is .8232
  * There are few predicted delays and a lot of false negatives
  * On the “actual delayed” row, 121 flights were predicted to be true positive. This means that out of the 47,885 delayed flights used in the test, only 121 were predicted correctly, while the rest were predicted “on time” when the flights were actually “delayed.”
 * Of the actual on-time flight row, 222,768 were true negative. This means that out of the 222,850 on-time flights used in the model, 222,768 were predicted correctly, while the rest were predicted as “delayed” when the flights were actually “on time.” 
* Precision 
 * The precision score is 0.60. Of the 203 flights predicted to be delayed, 121 were delayed.This model is somewhat reliable for positive classification. 
* Sensitivity
 * The sensitivity score is very, very low (0.00). The likelihood of predicting a delayed flight is very low. The model is missing a lot of positive results. 
* Feature Importance 

