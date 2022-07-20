# DMV Airport Efficiency Final Project

## Overview: 
For our project we are looking at the efficiency of local DC, Maryland, and Virginia (DMV) Airports for outbound domestic flights. Specifically we will be pulling data across Baltimore Washington International (BWI), Dules International Airport (IAD), Ronald Reagan Washington National Airport (DCA) from January 2019 through March 2022. Our group will be using the following data points to determine the best run airport:

* Month/Year/Day of week
* Operating airline
* Airport
* Destination
     * NorthEast, SouthEast, MidWest, SouthWest, West
* Scheduled Take Off Time
* Weather
* Actual Departure


## Presentation 
[Presentation](https://docs.google.com/presentation/d/1YszyuInGDuC_et4G8m_60k3zDEPiCfOyu6jOvvO_-Hg/edit#slide=id.gf47a8fbfff_1_0)

## Reasoning For Our Project:

As we approach post-pandemic normalcy, we can agree that a vacation (for whatever reason) is long overdue. Making up for lost time, especially while traveling, is something truly important to us. Once we've completed this project, we can use this information to plan trips and share with others outside of academia. Working with our large dataset is also allowing us to use what we've learned thoughout our class to practice real world situations.

## Data Source:

We worked with a couple websites to pull data for our project. The United States Department of Transportation provided statistics on Avaiation Data that We filtered through to grab specific inputs for our analysis. The National Oceanic and Atomspheric Administration provided daily weather summaries used in our analysis as well, as it coincideds with delays.

[Bureau of Transportation Statistics (BTS)](https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FGK&QO_fu146_anzr=b0-gvzr)

* year/month/day of week
* flight date
* Operated_or_Branded_Code_Share_Partners
* Origin
* Dest
* DestStateName
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

[National Oceanic and Atmospheric Administration (NOAA)](https://www.ncdc.noaa.gov/cdo-web/datasets)

* WSF2 - Fastest 2-minute wind speed
* WSF5 - Fastest 5-second wind speed
* SNOW - Snowfall
* WT03 - Thunder
* WT04 - Ice pellets, sleet, snow pellets, or small hail"
* PRCP - Precipitation
* WT05 - Hail (may include small hail)
* TOBS - Temperature at the time of observation
* WT06 - Glaze or rime
* WT08 - Smoke or haze
* SNWD - Snow depth
* WT09 - Blowing or drifting snow
* WDF2 - Direction of fastest 2-minute wind
* AWND - Average wind speed
* WDF5 - Direction of fastest 5-second wind
* PGTM - Peak gust time
* WT11 - High or damaging winds
* WT01 - Fog, ice fog, or freezing fog (may include heavy fog)
* TMAX - Maximum temperature
* WESD - Water equivalent of snow on the ground
* WT02 - Heavy fog or heaving freezing fog (not always distinguished from fog)
* TAVG - Average Temperature.
* TMIN - Minimum temperature

### Link to data files on AWS:

[Data](data_files.md)

## Description of the Data Exploration Phase:

We began our data exploration with researching online sources of all flights in the U.S. Initially, we started combing through Kaggle and found information but it was limited. To provide an accurate analysis on our selected DMV airports, we needed to find enough Avaiaton data for pre-covid, peak covid, post-covid years. To validate our future findings, we considered bringing in general unemployement, Hotel/AirBnB, and pricing data. We ultimately decided against pulling inputs from said subjects due to not seeing a direct connection to the questions we want answered. The United States Department of Transportation website proved to be a dependable source for the 3 airports we are preforming our analysis on. The National Oceanic and Atomspheric Administration provided a weather summary that we wanted for our project as well. 

![bts dexterproject](https://user-images.githubusercontent.com/99618784/179411577-4f4184a2-d491-4d2f-aca9-9f6726e91548.PNG)



## Description of the Analysis Phase: 

The csv file that was provided after selecting our filters had millions of data points. Our focus is on delayed flights and delay time. As we clean up our data we set our types of delay to: weather, carrier, late aircraft delay(LAS), security, and national air system(NAS). Our analysis is specifically looking at outbound domestic flights so we simplified the destination to regions, to include Puerto Rico and the U.S Virgin Islands as non-continental regions. We are using SQL, Pandas, and Tableau to make sense of our data. 

![Screen Shot 2022-07-06 at 4 41 07 PM](https://user-images.githubusercontent.com/99618784/178156547-0f4734be-58cd-42f0-ab32-3ac893cf850e.png)

## Questions We Hope To Answer: 
Our main question -which Airport has been most efficient through the volatility of the past 3 years? That being said, we will be looking at what factors make up the answer.

* What month/day of the week is the best?
* Does month/day of the week matter?
* Which airlines preformed the best?
* How does weather affect delays?
* Does origin airport affect delay?
* Is there a correlation with destination region and flight delay?
* Which airport/airline has the most delays over the years?

### Database:

![Database ERD first draft](https://user-images.githubusercontent.com/99618784/178156404-6ebea7fa-4b84-4da8-b44f-9de8016d30ee.png)

### Machine Learning Model
After cleaning, we ran it through a logistic regression model. We chose this model because it helps us predict binary outcomes (delayed or not delayed) based on flight data from previous years. Before running the model, we had to adjust the data. First, we had to implement the countries to a higher level of categories (5 U.S Region). We also converted the categorical data (Airport, Airline, etc.) into dummy/indicator variables. On our first run of our model, we had 100% accuracy. After checking factor importance, we included the departure delayed variable in our x value. After dropping that variable, our model gave us a better representation of performance. Our accuracy score is 0.95, which made us more comfortable with our data pre-processing. In our fourth run, we dropped variables related to delays (drop CRS_DEP_TIME since we have flights in departure blocks) to ensure we had no variables that overlapped with delays. We believe our fourth run is the best way to run the model to avoid any overlapping. image
![image](https://user-images.githubusercontent.com/100107588/179887371-1fd922da-5324-4269-b08c-02017150b007.png)
The accuracy score is 0.501; the model is only 50% accurate. the sensitivity score is 1.00 The precision is .59. Of the 190 flights, only 113 had been actually delayed.

The logistic regression is easier to implement, interpret, and train. We encountered some limitations that we discovered in our first run, and we had to look through the variables because the model was not predicting an accurate result. Our goal in the next few days is to run our data through a classification tree model and a neural network model. We uploaded a preliminary decision tree code that needs some adjustments. We will compare all three and their functionality with our data.
## Dashboard

As we create our dashboard in Tableau, our data begins to tell a story. When booking flight, one of the first choices you have to make is "When are you traveling". While looking at the images below you may notice that Wednesdays and Thursdays outbound domestic flights are more likely to be delayed out of BWI and DCA over any other day in the week. IAD holds the lowest amount of delayed flights overall for our DMV airports. If your wondering what causes these delays, your first thought may be weather. While certain weather conditions do cause delays, it may surprise you that its not nearly as impactful as a Carrier, Late Aircraft, or NAS delay. You will also have to decide which airline you'll chose to reach your destination. Our dashboard will go over those categories in more depth. In 2018, at a glance, you'll quickly learn not to book through Southwest Airlines if your flying out of BWI. These visuals of validating efficiency for our local airports are what we look forward to presenting to our stakeholders.

![Delays_By_Weekdays_Per_Airport](https://user-images.githubusercontent.com/99618784/179883159-a87a511e-d25b-4747-abee-60de10cc1233.png)

![Carrier Flights Per Year Per Airport](https://user-images.githubusercontent.com/99618784/179883125-d7ca2e20-fde5-4f9b-9c94-2f12942a19d3.png)

![Carrier Flights Per Year Per Airport](https://user-images.githubusercontent.com/99618784/179887115-53071c52-c864-4934-8196-edd47d3d6012.png)




### Communication

We've made the most of our time in class and using office hours to get together as well. We check in with questions, ideas, status updates through Slack. We have also met after class and on weekends to further work on our project. We plan on meeting outside of class at least twice a week. One of our group members set up a Zoom account so we are not limited to 40 minute sessions. Sunday mornings are our go to meet time. 

### Technology

The technolgies we will be using can be seen [here](technology.md)
