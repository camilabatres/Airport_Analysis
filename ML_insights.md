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
  ![image](https://user-images.githubusercontent.com/100107588/181672437-4a392186-4f87-438e-8124-e8c7e7a59eb2.png)
  * There are few predicted delays and a lot of false negatives
  * On the “actual delayed” row, 121 flights were predicted to be true positive. This means that out of the 47,885 delayed flights used in the test, only 121 were predicted correctly, while the rest were predicted “on time” when the flights were actually “delayed.”
  * Of the actual on-time flight row, 222,768 were true negative. This means that out of the 222,850 on-time flights used in the model, 222,768 were predicted correctly, while the rest were predicted as “delayed” when the flights were actually “on time.” 
* Precision 
  * The precision score is 0.60. Of the 203 flights predicted to be delayed, 121 were delayed.This model is somewhat reliable for positive classification. 
* Sensitivity
  * The sensitivity score is very, very low (0.00). The likelihood of predicting a delayed flight is very low. The model is missing a lot of positive results. 
* Feature Importance 
![image](https://user-images.githubusercontent.com/100107588/181672475-984983d3-187a-4cc3-a440-882ed8d1729e.png)
![image](https://user-images.githubusercontent.com/100107588/181672503-f48748f1-21fc-4d67-9949-397aae8392be.png)
* Above is a graph demonstrating each feature's importance in this model. The five most influential features (positive number) are Year and different time departures.  
* We believe the logistic regression performance is poor because of the low number of predicted delayed and low sensitivity scores. Therefore, we decided to use other models to find out if there is one that can process our data better. 

### Decision Trees ###
* Same preprocessing steps as logistic regression.
![image](https://user-images.githubusercontent.com/100107588/182034131-7452a681-6b07-4950-b113-55278b5842a9.png)

* Accuracy 
  * The accuracy score is .8164
  * There are a lot more predicted delays than the logistic regression model
  * On the “actual delayed” row, 13,954 flights were predicted to be true positive. This means that out of the 48,242 delayed flights used in the test, only 13,954 were predicted correctly, while the rest were predicted “on time” when the flights were actually “delayed.”
  * Of the actual on-time flight row, 203,376 were true negative. This means that out of the 222,768 on-time flights used in the model, 203,376 were predicted correctly, while the rest were predicted as “delayed” when the flights were actually “on time.” 
* Precision
  * The precision score is 0.42. Of the 33,071 flights predicted to be delayed, 13954 were delayed. This model is somewhat reliable for positive classification. 
* Sensitivity 
  * The sensitivity score is very low (0.29). The likelihood of predicting a delayed flight is very low. The model is missing many positive results.
* Feature Importance 
 ![image](https://user-images.githubusercontent.com/100107588/182034137-0f50bb2a-1577-4767-8cd1-8b66630c6767.png)
![image](https://user-images.githubusercontent.com/100107588/182034149-f0775f09-78a1-4eec-ae0e-394f2f9ade92.png)
  * Above is a graph demonstrating each feature's importance in this model. The five most influential features (positive number) are the day of the month, day of the week, month, year, and region southeast. 
  * We believe the Decision Tree is a better performing model with higher precision and sensitivity. We still chose to run a random forest model to see how that model performs. 
 
 ### Random Forest ###
 ![image](https://user-images.githubusercontent.com/100107588/182034526-74d4202f-7e03-49d9-945a-526063163e3f.png)
 * Accuracy 
   * The accuracy score is .82
   *  On the “actual delayed” row, 12,389 flights were predicted to be true positive. This means that out of the 48,242 delayed flights used in the test, 12,389 were predicted correctly, while the rest were predicted “on time” when the flights were actually “delayed.”
   * Of the actual on-time flight row, 208,639 were true negative. This means that out of the 222,493 on-time flights used in the model, 208,242 were predicted correctly, while the rest were predicted as “delayed” when the flights were actually “on time.” 
* Precision 
   * The precision score is 0.47. Of the 26,243 flights predicted to be delayed, 12,389 were delayed. This model is somewhat reliable for positive classification. 
* Sensitivity 
   * The sensitivity score is 0.26, which is also low. The likelihood of predicting a delayed flight is low. The model is missing many positive results.
* Feature Importance  
![image](https://user-images.githubusercontent.com/100107588/182034533-e75de25e-eeea-4665-b0db-0f183bc78d23.png)
![image](https://user-images.githubusercontent.com/100107588/182034534-c0dc21ae-fe8b-4fcc-a471-be3eaaddab63.png)
   * The five most important features are above. Day of the month is the most important x feature in this model. The rest of the features are also related to the date: month, year, and day of the week. When you fly out is the most influential feature in this model. 

 ### Neural Network ###
![image](https://user-images.githubusercontent.com/100107588/182034711-966538d0-ccdd-4b54-b422-7d65acccc06b.png)
* Accuracy 
   * The accuracy score is .83
   * On the “actual delayed” row, 3,898 flights were predicted to be true positive. This means that out of the 47,885 delayed flights used in the test, 3,898 were predicted correctly, while the rest were predicted “on time” when the flights were actually “delayed.”
   * Of the actual on-time flight row, 220,130 were true negative. This means that out of the 222,850 on-time flights used in the model, 220,130 were predicted correctly, while the rest were predicted as “delayed” when the flights were actually “on time.” 
* Precision 
   * The precision score is 0.59. Of the 6,618 flights predicted to be delayed, 3,898 were delayed. This model is somewhat reliable for positive classification. 
* Sensitivity 
   * The sensitivity score is 0.08, which is very low. The likelihood of predicting a delayed flight is low. The model is missing many positive results. 
*Feature Importance 
![image](https://user-images.githubusercontent.com/100107588/182034861-0f4407fc-0e37-4de8-bd44-fa0c96281eb8.png)
![image](https://user-images.githubusercontent.com/100107588/182034884-ca147e96-4655-4da7-9e9c-5f794efedd3d.png)
   * Above is a graph demonstrating each feature's importance in this model. The five most influential features (positive number) are the year, covid, departure times, and UA airline. This is the only model that has covid in the top 5 most influential features. 

## Comparing All The Models 
![image](https://user-images.githubusercontent.com/100107588/182035393-5d36c823-27cb-4f17-abb2-17924c2e040a.png)




