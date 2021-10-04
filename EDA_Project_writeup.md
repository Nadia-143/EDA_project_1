# MTA Turnstile Exploratory Data Analysis 

## Abstract 

The purpose of this project is to make an exploratory data analysis for the New York subway MTA turnstile data and provide the WTWY with some recommendations to deploy their street teams based on: the top 10 busiest stations, the busiest days and time related to each station in that list. The data was retrieved from Metropolitan Transportation Authority website: (http://web.mta.info/developers/turnstile.html). After exploring and analyzing data, we plot some visualizations and graphs to assure that we achieve the purpose of this project. 

## Design 
 The analysis started by scrapping three months of data from 29 May to 27 August and create a database out of them in SQLIte3. Then, some cleaning for the data was done such as adding some columns, dropping others, and clearing outliers there. Finally, plotting the graphs helped us get more insight and intuitions about the average traffic.

## Data

The New York subway MTA turnstile data is a series of data files containing cumulative number of entries and exits by station, turnstile, date and time. Each file contains 7 day-data which records are collected typically every 4 hours with some exceptions. The data frame used here from (29/5/2021 – 27/8/2021)

Structure of the data 
```

>> C/A = Control Area (e.g., A002) 
>> unit = Remote Unit for a station (e.g., R051)
>> SCP = Subunit Channel Position represents an specific address for a device (e.g., 02-00-00)
>> Station = Represents the station name the device is located at
>> date = Represents the date (MM-DD-YY)
>> time = Represents the time (hh:mm:ss) for a scheduled audit event
>> desc = Represent the "REGULAR" scheduled audit event (Normally occurs every 4 hours)
>> entries = The cumulative entry register value for a device
>> exits = The cumulative exit register value for a device
```

## Analysis Steps 

First, scrapped the data and sort them into a sql db consisting of  one table holding all the information of the Subway MTA. Then, by using sqlAlchemy library in jupyter notebook we read the data as a dataframe. After that, performed some cleaning for the data; adding some additional columns to help us depict what is going on and understanding the data clearly. Moreover, dropping unnecessary columns such as line name desc,… etc helped us see the complete vision clearly. Finally, by using some powerful libraries in python(pandas ,matplotlib ,seaborn …etc), we were able to do the analysis of the data easily. The main purpose of the project was achieved. Plotting graphs and visualizations showed the most busiest station, the busiest hour and days for each station which we desired for. 


## Conclusion and summary 

1.from the above Exploratory Data analysis we can conclude that the most traffic station is the "world trade CTR" station as we see this from the above plots. we also can deduce that the top 10 stations which have most traffics are ['WORLD TRADE CTR', '191 ST', 'BAY RIDGE AV', 'HUNTS POINT AV', '4AV-9 ST', '96 ST-2 AVE', 'TREMONT AV', 'CROWN HTS-UTICA', '207 ST', 'BOWERY']. Also we can see that Monday is the most traffic day for the "world trade CTR " and at time 12 AM is the busiest hour traffic in the day.
2.the most busiest day for "191 ST " Station is Thursday
3.4 AM is the most traffic hour at Wednesday At "BAY BRIDGE AV" station.
4.the most busiest day for "HUNTS POINT AV " Station is Monday
5.the most busiest day for "4AV-9 ST " Station is Thursday
6.the most busiest day for "96 ST-2 AVE " Station is Monday
7.6.the most busiest day for "TREMONT AV " Station is Tuesday

