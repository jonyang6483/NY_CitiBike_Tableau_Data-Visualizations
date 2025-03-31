# NY_CitiBike_Tableau_Data_Visualizations

### **[Link to Tableau Viz](https://public.tableau.com/app/profile/jonathan.yang1344/viz/CitiBikeDataVisualizationAnalysis/CitiBikeData-Story)**

### Analysis at Bottom

## Data
I collected the December 2024, January 2025, and February 2025 data from the [New York CitiBike data website](https://s3.amazonaws.com/tripdata/index.html).

This data had the following fields:

- Ride ID
- Rideable type
- Started at
- Ended at
- Start station name
- Start station ID
- End station name
- End station ID
- Start latitude
- Start longitude
- End latitude
- End Longitude
- Member or casual ride

In [`Cleaned_Data.ipynb`](Cleaned_Data.ipynb), I combined the three CSV files. Due to the size limit of Tableau being 1 GB, I had to reduce the data to get a smaller file size. To do so, I:
- removed the `ride_id` column as it was unused
- converted the `member_casual` column to `True`/`False` rather than strings
- mapped the values of the `rideable_type` column to single characters rather than full strings
    - "classic_bike"  -> "C"
    - "electric_bike" -> "E"
- dropped all rows that were missing any data

## Tableau
The single csv file was then added to Tableau and visualizations were created to explore different trends and phenomena. Due to the size-limited amount of data, I was unable to examine long trends over multiple seasons or year.

> NOTE
>
> Tableau on web does not appear to respect fixed size Story and Dashboards.

**[Link to Tableau Viz](https://public.tableau.com/app/profile/jonathan.yang1344/viz/CitiBikeDataVisualizationAnalysis/CitiBikeData-Story)**

### Images of The Four Story Pages
![Tableau Story Page 1](Images/%20CitiBike_Map_All_Stations-%20Story1.png)
![Tableau Story Page 2](Images/CitiBike_Total_Statistics%20-%20Story2.png)
![Tableau Story Page 3](Images/CitiBike_Popular_Stations%20-%20Story3.png)
![Tableau Story Page 4](Images/CitiBike_Time%26Day_Statistics%20-%20Story4.png)

## Analysis

In order from the Tableau Story:

1. **CitiBike Map**

    The map shows all starting locations the New York City CitiBike program. Using the slider on the right, you can see how new stations have been added, primarily in the South East of the city. The most popular starting locations for rides remains in Central Manhattan for all three months.

2. **Total Statistics**

    On this dashboard we see the total values for the winter season. Here we see some interesting information.
    - While the vast majority of rides are half an hour or less, decreasing as time goes on, the number of very long rides stays relatively constant.
    - Most rides are a under a mile to their ending station. 
    - Non-Member ride time is on average about 13 to 14 minutes, nearly almost about 50% longer compared to the Member ride time. However, both travel about the same average distance of a little over 1 mile. This could be due to many Non-Members being tourists, making stops between their destinations or being unfamiliar with the area.

3. **Popular Stations**

    The most popular stations for beginning and ending rides are in Central Manhattan. This is likely due to the high density of housing and population, as shown in the background layers of the two maps.
    - It is also interesting to notice that the stations have almost the exact same number of beginning and ending rides per station. We can conclude that many users are consistently using the same station twice a day, possibly commuting to and from  work or school.

4. **Time & Day Statistics**

    On this dashboard, we can see usage for each day in our three-month winter season, as well as usage by day of the week and hour of the day.
    - From the visualizations, we can see the most common days and times to use the bikes is during the commuting hours on weekday. This further reinforces the conclusion from the popular stations section that commuting is a major use case of the bikes.
    - We also see an increase in the early afternoon hours on weekends, but dropping off quickly around 5:00 PM, around the time of sunset in New York City during the winter months.
    
<hr>

### Potential Future Analysis
- Use weather data to see how temperature and precipitation affect usage.
- Use age and gender data to look for more trends. (This data is no longer included in the public download)
- Use more data over years to find rider growth and yearly trends.
- Use membership data to find out how much the average individual member uses CitiBike.

