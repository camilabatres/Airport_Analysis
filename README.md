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


![Screen Shot 2022-07-06 at 4 41 07 PM](https://user-images.githubusercontent.com/99618784/178156547-0f4734be-58cd-42f0-ab32-3ac893cf850e.png)

## Reasoning For Our Project: 

As we approach post-pandemic normalcy, we can agree that a vacation (for whatever reason) is long overdue. Making up for lost time, especially while traveling, is something truly important to us. Once we've completed this project, we can use this information to plan trips and share with others outside of academia. Working with our large dataset is also allowing us to use what we've learned thoughout our class to practice real world situations.

## Data Source: 

We worked with a couple websites to pull data for our project. The United States Department of Transportation provided statistics on Avaiation Data that We filtered through to grab specific inputs for our analysis. The National Oceanic and Atomspheric Administration provided in depth weather patterns that we used for our analysis as well, as it coincideds with delays.

https://www.transtats.bts.gov/DL_SelectFields.aspx?gnoyr_VQ=FGK&QO_fu146_anzr=b0-gvzr

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


https://www.ncdc.noaa.gov/cdo-web/datasets

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

### Link to merged csv file:
https://drive.google.com/file/d/1fOjVoigY-u8OIQptRxF75AVX-LMx3trb/view?usp=sharing

## Questions We Hope To Answer: 
Our main question -which Airport has been most efficient through the volatility of the past 3 years? That being said, we will be looking at what factors make up the answer. 

* What month/day of the week is the best?
* Does month/day of the week matter? 
* Which airlines preformed the best? 
* How often does weather effect delays? 
* Does Destination effect travel efficiency? 

### Database:

![Database ERD first draft](https://user-images.githubusercontent.com/99618784/178156404-6ebea7fa-4b84-4da8-b44f-9de8016d30ee.png)




### Communication

We've made the most of our time in class and using office hours to get together as well. We check in with questions, ideas, status updates through Slack. We have also met after class and on weekends to further work on our project. We plan on meeting outside of class at least twice a week.
