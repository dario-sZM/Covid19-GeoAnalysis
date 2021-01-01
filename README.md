# Covid19-GeoAnalysis

A pandemic. The deepest global recession since the Second World War. Governmental mismanagement and some of the largest protests in history. 2020 shaped up to be a record breaking year. Let's see how we have shaped up against COVID-19 a year later!

## Expectation
1. Visualize COVID-19 [Global Maps, Density Plots and Individual Continents]
2. Adapt the SIR Model, Diffusion Reaction and Polynomial Regression
3. Find the R0 
4. Create a variable model for the new Confirmed, Recovered and Deaths
5. Impulse-Response Function
6. Forecast / Predict the futhur spread of the pandemic across Africa

## Data

Datasets: <br>
https://www.worldometers.info/ <br>
https://www.kaggle.com/sudalairajkumar/novel-corona-virus-2019-dataset <br>
https://github.com/CSSEGISandData/COVID-19 <br>

We will use the following two csv files from the datasets above: 
````
1. geofile = './datasets/covid_19_clean_complete.csv'

Data columns (total 10 columns):
 #   Column          Non-Null Count  Dtype  
---  ------          --------------  -----  
 0   Province/State  14664 non-null  object 
 1   Country/Region  49068 non-null  object 
 2   Lat             49068 non-null  float64
 3   Long            49068 non-null  float64
 4   Date            49068 non-null  object 
 5   Confirmed       49068 non-null  int64  
 6   Deaths          49068 non-null  int64  
 7   Recovered       49068 non-null  int64  
 8   Active          49068 non-null  int64  
 9   WHO Region      49068 non-null  object 


2. covidfile = './datasets/covid_19_data.csv'

Data columns (total 8 columns):
 #   Column           Non-Null Count   Dtype  
---  ------           --------------   -----  
 0   SNo              172480 non-null  int64  
 1   ObservationDate  172480 non-null  object 
 2   Province/State   124597 non-null  object 
 3   Country/Region   172480 non-null  object 
 4   Last Update      172480 non-null  object 
 5   Confirmed        172480 non-null  float64
 6   Deaths           172480 non-null  float64
 7   Recovered        172480 non-null  float64

````

## Exploratory Data Analysis
There is very litle needed to clean the data before continuing. 
We can however, drop the column containing the provincial information as this is blank for the majority of reported cases. 

````
geo_data = geospatial.drop(columns=['Province/State'])
covid_data = covid19.drop(columns=['Province/State'])
````
And to match what we see in worldometer, let's plot the total wordwide cases just for reference: 

// Insert total cases chart //

## Data Visualization
The data above gives us comprehensive access to the total cases in each indidual country, as well as recoveries, deaths and active cases. This gives us the ability to map out the full spectrum of the pandemic using the geopandas library. 

### Conventional World Map View
Already, we can see that Africa and Australasia have seen far less cases than the surrounding continents. However, due to the nature of the map I don't believe we really grasp the magnitude of case difference across the world. 

// INSERT GLOBAL CHART // 

### Bubble Map
Let's take this representation in a different direction then... <br>
You can see below a density plot of cases per country (longitude and latitude) which proves to be a far better representation of the Impact of COVID-19 worldwide. 
<br>
Here we see a much more prominent difference in case density across the world. Africa and Australia are just barely rocognisable compared to the surrounding continents. 

// Insert bubble map // 

### Contour Map
If we trun to seaborn for a jointplot, we can map out the density of the COVID-19 cases uses a map similar to contours. It emphasises the prominence of the pandemic within the Northern Hemisphere. 
And in the case of the southern hemispher, it is very much concenrated towards South America. 

// Insert contour map ///

