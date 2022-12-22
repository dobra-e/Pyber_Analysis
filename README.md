# Pyber_Analysis
## Overview
PyBer, a ride-sharing company valued at $2.3 billion, was interested in exploring trends in rideshare data from January to May 2019. Included in the datasets were the following fields:
* city
* driver_count
* type
* date
* fare
* ride_id

### Purpose
The purpose of the analysis was to identify differences in ride-sharing patterns between city types to inform decision-making at PyBer. In particular, the goal is to improve accress to ridesharing services and determine affordability for underserved neighborhoods.

### Analysis
#### Ride-Share DataFrame
First, the two datasets, city_data.csv and ride_data.csv, were merged on the city variable to create a single dataframe. Next, `groupby` was used to summarize new series variables by city type. The resulting series were then combined into a new dataframe and formatted to show the ride-share data by city type.

#### Total Weekly Fares by City Type
Again using `groupby`, a new dataframe was created with 'type' and 'date' as the indices and the fares for each date summed. The index was then reset and the `pivot()` function was used to create a pivot table with 'date' as the index, 'type' as columns, and 'fare' as values. The table was filtered to only include rides between January 1, 2019 and April 28, 2019. After converting the index to a datetime data type, `resample()` and `sum()` were used to group the data into weeks and to total the fares. A plot was then produced to illustrate the total weekly fares by city type. 

## Results
#### Ride-Sharing by City Type Table
The table resulting from the analysis is below. 
![DataFrame Summary Table](/analysis/SummaryDataFrame.png)

As shown in the table, urban cities have the highest total rides, total drivers, and total fares. However, the average fare per ride is lower than both suburban and rural cities. Unlike suburban and rural cities, urban cities have more total drivers than total rides. 

#### Total Weekly Fares by City Type Plot
The plot resulting from the analysis is below.
![Total Weekly Fares Plot](/analysis/Pyber_fare_summary.png)

Consistent with the table above, the plot shows that urban cities produced the highest total fares each week. Across all city types, there is a spike in total fares in the third week of February. Rural cities had the least variability in total fares across the selected timeframe, while urban cities had the most.

## Summary
Based on the analysis, recommendations can be made to address disparities in ride-sharing between city types.

### Recommendations
1. Focus advertising and investment in urban cities to increase ridership. Urban cities have an excess of drivers that can accommodate an increase in riders. 
2. Increase the number of drivers in rural and suburban areas. These markets are likely taking longer rides meaning there may be longer wait times detering potential customers from using the service.
3. Charge an increased rate per mile or minute for urban rides. This would increase the average fare per ride and help close the gap between the urban and suburban or rural markets. 
