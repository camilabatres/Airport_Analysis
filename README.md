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

![Screen Shot 2022-07-06 at 4 41 07 PM](https://user-images.githubusercontent.com/99618784/178156547-0f4734be-58cd-42f0-ab32-3ac893cf850e.png)

## Presentation 
https://docs.google.com/presentation/d/1YszyuInGDuC_et4G8m_60k3zDEPiCfOyu6jOvvO_-Hg/edit#slide=id.gf47a8fbfff_1_0

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
We will first use the logistic regression to predicts binary outcomes. I added a pandas file that demonstrates how we will process our data to make our predictions (sample_logistic_regression)  [sample code](https://github.com/camilabatres/dexter_project/blob/machine_learning_model/sample_logistic_regression.ipynb)

input data: 
year/month/day of week
flight date
Origin
Dest
DestStateName
Crsdeptime
Deptime

output: 

1: delayed flights or 0: not delayed flights.
This will help us determine which flights will be delayed under the input (above) conditions Since the data is not continous, we would use the line of code below to find out the probablity after training it. log(probability of delay/(1 - probability of delay))

### Communication

We've made the most of our time in class and using office hours to get together as well. We check in with questions, ideas, status updates through Slack. We have also met after class and on weekends to further work on our project. We plan on meeting outside of class at least twice a week.

### Technology

The technolgies we will be using can be seen [here](technology.md)
