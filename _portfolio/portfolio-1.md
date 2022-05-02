---
title: "Exploring MTA Turnstile Data"
excerpt: "data project 1 <br/><img src='/files/fig/proj1/01_00_turnstile.jpg'>"
## excerpt: "data project 1 <br/><img src='/images/500x300.png'>"
collection: portfolio
categories: [Data Science, Project]
---

![Turnstile](/files/fig/proj1/01_00_turnstile.jpg?raw=true)

## Introduction
This blog is built on my first data science project at Metis/Chicago, working together with Zach Heick and Eric Chan.


## Background
Our client, WomenTechWomenYes (WTWY), will host an annual gala fundraising event at the beginning of summer next year in New York City. They want to place their street teams at entrances of subway stations and distribute posters to advertise this event. The objective of this project is to isolate *popular subway stations* to maximize the potential attendees to the fundraising event.


## Approach
### Raw data and tools
1. The main data set we used is the [MTA turnstile data](http://web.mta.info/developers/turnstile.html), which shows the entries and exits for each turnstile device at subway stations in NYC. The raw data was shown with a screenshot in Figure 1 below. For each device, entries and exits were documented accumulatively every 4 hours.
2. The other source of data is the housing value from [Zillow](https://www.zillow.com/research/data/). It is assumed that the housing price indicates the ability and likeness of donations.
3. The main tools used are pandas (data exploration) and matplotlib (plotting and visualization), both implemented in Python.

<center><img src="/files/fig/proj1/01_01_mta_raw_data.png" width="600"></center>
<center>Figure 1. An example of stations.</center>


### Data Manipulation and Visualization
We analyzed net entries of line & station combinations over time and cleaned the data by removing unrealistic spikes (possibly caused by the counter reseting).


## Results & Discussion
### Pick a station
First of all, we summarize the riders for each station, as shown in Figure 2. Such figure indicates that busy stations are mostly located in manhattan.

<center><img src="/files/fig/proj1/01_02_stations.png" width="700"></center>
<center>Figure 2. Busiest NYC Subway Stations in May 2017 </center>

### Pick a time
Besides identifying popular stations, we plot out the variation of entries over time, as indicated in Figure 3 below. The weekdays (represented by the wide peaks) have more riders that the 2-day weekends (narrow valley). We would suggest weekdays for the flyer distribution.

<center> <img src="/files/fig/proj1/01_03_days.png" width="1000"></center>
<center> Figure 3. NYC Subway Station Entries by Day </center>


### Cross-reference with Zillow data
Figure 4 below reveals the housing value against subway entries. Considering the combinations of the number of potential guests (how many people would donate) and economic capabilities (how much money would they donate), 14 ST at Union Square and 42 ST-Port AUTH stand out.

<center> <img src="/files/fig/proj1/01_04_pillow.png" width="500"></center>
<center> Figure 4. Housing Value and Entries by Station </center>

## Conclusions
We suggest following three stations:
1. 14 ST at Union Square
2. 42 ST-Port AUTH
3. Grand central

Top two are the best combinations of subway entries and housing values. Grand Central Station would be also recommended as it is the busiest station with most riders.


## Further considerations
In order to further improve the accuracy of prediction with the data science knowledge, there are several additional factors we could consider.
1. **Station**: For example, subtracting the tourist riders would lead to better results. Furthermore, those stations close to the gala host place could be suggested with a high confidence (probably by adding a weighting coefficient).
2. **Time**: We suggest weekdays with more riders than the weekend, but people taking the subway during the rush hour are probably less patient to look at the poster.
3. **Other data**: Last but not least, there are more relevant data sources, which could be helpful in future prediction. For example, private data from [WiTNY - Women in Tech New York](https://www.meetup.com/Women-in-Tech-New-York/) (> 1,000 members!) could be very insightful and help narrow down and navigate to the ideal attendees to this specific event.

## References
1. Front image: [www.nycedc.com](https://www.nycedc.com/blog-entry/using-mta-turnstile-data-examine-land-use)
