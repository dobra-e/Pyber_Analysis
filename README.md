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

As shown in the table, urban cities have the highest total rides, total drivers, and total fares. However, the average fare per ride is lower than both suburban and rural cities. Unlike suburban and rural cities, urban cities have more total drivers than total rides. 

#### Total Weekly Fares by City Type Plot
The plot resulting from the analysis is below.

Consistent with the table above, the plot shows that urban cities produced the highest total fares each week. Across all city types, there is a spike in total fares in the last week of February. Rural cities had the least variability in total fares across the selected timeframe, while urban cities had the most.

## Summary

