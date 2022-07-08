# Airport Efficiency Analysis Final Project

## Overview: 
For our project we are looking at the efficiency of local DMV Airports for outbound domestic flights. Specifically we will be pulling data across Baltimore Washington International(BWI), Dules International Airport(IAD), Ronald Reagan Washington National Airport(DCA) from January 2019 through March 2022. Our group will be using the following data points to determine the best run airport: 

* Month/Year/Day of week
* Operating airline
* Airport
* Destination
     * NorthEast, SouthEast, MidWest, SouthWest, West
* Scheduled Take Off Time
* Weather
* Actual Departure

## Reasoning For Our Project: 
As we approach post-pandemic normalcy, we can agree that a vacation (for whatever reason) is long overdue. 

## Data Source: 

We worked with a couple websites to pull data for our project. We filtered through the raw data to grab specific inputs for our analysis. 

https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FGK&QO_fu146_anzr=b0-gvzr

* year/month/day of week
* flight date
* marketing airline network
* Operated_or_Branded_Code_Share_Partners
* Origin
* Dest
* Crsdeptime
* Deptime
* Depdelay
* Departure delay groups
* Dep time block
* Cancelled
* Diverted
* Carrier delay
* Weather delay
* Nas delay
* Security delay
* Lateaircraft delay

https://www.ncdc.noaa.gov/cdo-web/datasets

## Questions We Hope To Answer: 

* What month/day of the week is the best?
* Does month/day of the week matter? 
* Which airlines preformed the best? 
* How often does weather effect delays? 
* Does Destination effect travel efficiency? 

## Machine Learning Plan 
We are planning to find out which model is the best machine learning model for our analysis. We will decide between the supervised machine learning and unsupervised machine learning. With supervised, we would like to see if a regression model works to display the changes over the years. with unsupervised, we would like to see if the types of categorization or the posibility of displaying the data through a neural net to give it a total different outlook. 
Once we choose the best model that works best for our questions, we will connect it to the weather data. 
Below is a chart to display our model 

