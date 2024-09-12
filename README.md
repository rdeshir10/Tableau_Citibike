# CitiBike Analysis 2017-2019

Link to Tableau Public workbook: https://public.tableau.com/app/profile/ardeshir.pashootan/viz/CitiBikeChallenge_17260054909130/BusiestHours

## Data Cleaning & Transformation Overview (Source files were not loaded as they were too large)
- **Data Loading**: Imported CitiBike trip data with key fields like start/end times, station locations, and user demographics.
- **Condensing Data**: Since the data available was incredibly large and I am working with Tableau Public, I had to condense the data set in order to reduce the computational stress. To keep the integrity of data intact I took measure to ensure that the data   
                       condensation was done randomly to ensure there were not any biases.  
- **Missing Values**: Handled missing or invalid data by removing or imputing values where necessary.
- **Date/Time Formatting**: Extracted year, month, day, and hour from datetime fields for time-based analysis.
- **Distance Calculation**: Applied the Haversine formula to calculate trip distances using latitude and longitude.
- **Generational Classification**: Segmented users into generational cohorts based on birth year for demographic analysis.
- **Data Aggregation**: Aggregated data by month and quarter to analyze trip durations and patterns.
- **Feature Engineering**: Added new fields (e.g., distance, generation, time) and removed irrelevant columns for streamlined analysis.

## Dashboards and interactivity:

### Trip Planner
This Dashboard uses the coordinates of all the stations and uses their coordinates to calculate the distance between start to end using Haversine formula. Furthermore it also gives you an estimated trip duration in minutes at an estimated speed of 15 km/hr. 

### Time Dashboard
This Dashboard allows a User to interactive with the data in a multidimensional manner. One can select options such as the generation, Month or quarter in a given year and will see the data across the dashboard filter accordingly. This enables you to understand the demographic of the users in a chronological manner of your choosing. 

### Popularity Dashboard
This Dashboard similarly allows the user to use generations, gender and user type to understand which stations are most popular amongst which generation. It can be filtered using both the generation and a range birth years should you want to be more specific. Additionally it allows you to further filter the data as per User type and Gender to dwell even deeper in understanding the popularity of stations. 

### CitiBike Story
To experience the visualizations and dashboard all in one. This story will take you through the entire analysis and allow you to interactive with data as you go along to make sense and make your own derivations. Upon completion you will be well informed on the purpose of the analysis and also be able to understand the data through your own curiosity, the interactivity in this story is specifically designed to enable the viewer to analyse the data to their liking. 

## 1) Stations Popularity - Generational 
Millennials and Generation X seem to account for the majority of CitiBike usage across most stations.  
This is reflected by the significant portions of orange (Millennials) and green (Generation X) in many of the bars, particularly in the most popular stations.  
This likely indicates that these two generations make up the majority of the bike-sharing population, which could be due to their urban lifestyle and active commuting patterns.  
Greatest Generation and Silent Generation (represented by blue and yellow bars) have much smaller proportions in bike usage, as expected.  
This could suggest that bike-sharing is less appealing or accessible to older generations, likely due to mobility challenges or other preferences for transportation.  
Generation Z (represented by red) shows some presence in CitiBike usage but doesn't dominate. However, they still contribute significantly to the overall share of users at certain stations.  
Their numbers are smaller than Millennials and Generation X, but their presence could increase over time as younger individuals continue to adopt biking as a mode of transportation.  

## 2) Periodic variance in usage 

### Quarterly:
2018 Q3 has the longest average trip duration, peaking at around 18 minutes, which is significantly higher than any other quarter.  
Trip durations from 2018 onward tend to be consistently higher than in 2017.  
In 2017, the average trip duration remains below 14 minutes across all quarters, showing a notable rise in trip duration over the years.  
2019 Q3 and 2019 Q4 show relatively stable averages around 15–16 minutes, indicating a leveling-off after the 2018 peak.  

**Potential Reasons**:  
The peak in 2018 Q3 could be attributed to factors like:  
- **Weather**: Summer months typically encourage longer trips.  
- **Tourism**: If there was an increase in tourist activity during that period, it might have resulted in longer trip durations.  
- **Special Events**: Events or festivals during Q3 2018 may have drawn more users for recreational purposes, increasing trip durations.

### Monthly: 
August stands out with the longest average trip duration, approaching 50 minutes.  
July and September also show high trip durations, indicating a clear summer trend where trips tend to be longer.  
December has the shortest average trip duration at about 25 minutes, with other winter months like January and February also showing relatively short trip durations.  
Months in spring and fall (March, April, May, October, November) display moderate trip durations between 35 to 45 minutes.  

**Potential Reasons**:  
- **Seasonality**: The spike in summer (July, August, September) and the drop in winter (December, January, February) are likely due to weather conditions:  
  - **Summer**: Longer daylight hours and warmer weather encourage users to take longer trips.  
  - **Winter**: Cold weather likely discourages prolonged bike rides, leading to shorter trips.  
- **Tourism and Events**: Summer months are typically peak tourist seasons, which may contribute to the increased trip durations during this period.  

## 3) Busiest Hours of Operation

### Male Peak Trip Times:
There is a notable spike at 21:00 (9 PM), with average trip durations reaching over 50 minutes for both subscribers and customers.  
Another smaller spike is seen around 16:00 (4 PM), where average trip duration is around 40 minutes.  
**Trip Count**: The highest trip count occurs during 21:00, where there are 1,181 trips, a significant increase compared to earlier hours.  
**Trend**: Most of the day sees relatively stable average trip durations between 10 and 40 minutes, with an increasing trend in the afternoon and a major spike in the evening.

### Female Peak Trip Times:
Female users show a similar trend to male users with a peak at 21:00 (9 PM), where the average trip duration exceeds 50 minutes for both user types.  
There's also a notable spike around 16:00 (4 PM).  
**Trip Count**: The highest trip count for females is also during 21:00, with 564 trips.  
**Trend**: Female users show a slightly less pronounced peak in trip duration compared to males, with more steady averages during the day.

### Unknown Gender Peak Trip Times:
The largest spike is at 17:00 (5 PM), where average trip duration for customers significantly surpasses 100 minutes. This spike is somewhat abnormal compared to male and female patterns.  
Another peak occurs at 16:00 (4 PM) with a smaller spike.  
**Trip Count**: The trip count peaks at 16:00 with 1,588 trips, indicating a busy time for users whose gender is not defined in the data.  
**Trend**: The unknown gender category shows erratic trip durations compared to the more stable trends seen with male and female users.

### Subscribers (Blue Area):
Subscribers generally have shorter average trip durations compared to customers, which aligns with the idea that subscribers may use the service more for routine commuting, where trips tend to be shorter.  
Subscribers tend to be more active earlier in the day, with a consistent number of trips throughout morning and afternoon hours.

### Customers (Orange Area):
Customers (non-subscribers) tend to take longer trips, particularly during peak hours (21:00 for males and females, and 16:00 for the unknown category).  
The significant trip duration spike at 17:00 for unknown gender users suggests that customers are driving this trend.  
Customers appear to engage more in leisure or non-commuting trips, which may explain their longer trip durations.
