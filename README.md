# Exploratory Data Analysis of MTA traffics
![](/img/header.png)
## Abstract 

The purpose of this project is to implement an exploratory data analysis on the New York subway MTA turnstile data and provide our clinet, an organization called WomenTechWomenYes(WTW) who is going to hold a summer gala and planning to allocate street teams in the entrances of the subway stations in order to maximize the number of sign-ups individuals and send them free invitations to attend their gala, with some recommendations in order to choose the optimal time and location for them to deploy their street teams; Our recommendations are based on three aspects: the top 10 busiest stations,the busiest month within our dateframe and the busiest days and time for each station among the top 10 stations. By planning our target and the way to acheive it, we retrieved the desired data from Metropolitan Transportation Authority website which is available to anyone: (http://web.mta.info/developers/turnstile.html).

## Design 
 As mentioned above, the EDA intiated by getting the data for the time frame we chose. We scrapped three months of data from 29 May to 27 August and created a database out of them in SQLIte3. Then, we did some cleaning for the data: such as adding some columns, dropping unnecessary ones and clearing outliers from total traffic column. Finally, we drew our conclusion based on the graphs and visualizations that we get after cleaning and preparing the dataframe; these figures helped us get wise and deep insight and intuitions about the location and time for street teams to canvas on. A word to mentioed all our graphs wasdetermined by the average daily total traffic.

## Data

The New York subway MTA turnstile data is a series of data files containing cumulative number of entries and exits by station, turnstile, date and time. Each file contains 7 day-data which records are collected typically every 4 hours with some exceptions. The data frame used here from (29/5/2021 – 27/8/2021)

Structure of the data 
```

C/A = Control Area (e.g., A002) 
unit = Remote Unit for a station (e.g., R051)
SCP = Subunit Channel Position represents an specific address for a device (e.g., 02-00-00)
Station = Represents the station name the device is located at
date = Represents the date (MM-DD-YY)
time = Represents the time (hh:mm:ss) for a scheduled audit event
desc = Represent the "REGULAR" scheduled audit event (Normally occurs every 4 hours)
entries = The cumulative entry register value for a device
exits = The cumulative exit register value for a device
```

## Analysis Steps 

First, we scrapped the data and sort them into a sql db consisting of one table holding all the information of the Subway MTA. Then, by using sqlAlchemy library in jupyter notebook we read the data as a dataframe. After that, we performed some cleaning for the data; adding some additional columns to help us depict what is going on and understanding the data clearly; getting rid of outliers from total traffic made the result more reliable. We did so by filling the outliers with median of that column. Moreover, dropping unnecessary columns such as line name desc,… etc helped us see the complete vision clearly. We plotted the top 10 stations determined by the total daily average traffic, and then we zoned in on which month within our time frame we chose WTWY street teams may want to canvas on. Thus, we compared the three months against each other. Lastely, we analyzied these stations by part of time to find the optimal time range for street teams to allocate in stations.By doing all of that the main purpose of the project was achieved. 

## Conclusion and summary 


From the Exploratory Data analysis we went through, we would recommend targeting stations that have a high traffic to maximize the number of sign-ups people to attend the gala, thus our recommendation is based on most busiest stations and busiest hours during weekdays. Therefore, we conclude that June and July are best months for  their street teams to canvas on. Also, From the analysis and figures we found that the top 4 stations in terms of traffic station are **34 St-Penn STA ,FULTON ST,23 ST and GRD CNTRL-42 ST** repectively. All of them are agree on that ideal visiting starts from midday until 8:00 pm roughly. The following shows the optimal timing and days for each station to be visited:  
  > 1- 34 St-Penn STA  from Monday through Friday between ( 8:00 am – 8:00 pm ) 
& Saturday between ( 12:00 pm – 8:00 pm ) 
>
> 2- FULTON ST from  Monday through Friday between ( 12:00 pm – 4:00 pm ) .
>
> 3- 23 ST from Monday through Friday between ( 8:00 am – 8:00 pm ) . 
>
> 4- GRD CNTRL-42 ST from Monday through Friday from ( 12:00 pm – 8:00 pm ) & Thursday from ( 4:00 am – 8:00 am ) .


