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
