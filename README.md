![Pyber_cover](https://user-images.githubusercontent.com/22451540/151674464-50d4a859-cbbb-41f0-8bb9-a6817f332449.PNG)

# PyBer Analysis

## Overview of the analysis
### Purpose
A well-known company assigned us the task of analyzing the trends in their ride-sharing app. They work all over the country, but have been seeing different results in the different areas they work. Throughout the week, we analyzed the data, cleansed it and provided some very useful graphs to study the distribution and the relationship between type of city, drivers and fares. However, the company has requested a deeper analysis, in order to understand how time has an effect in the users behavior.
With the data provided by PyBer we will create a multiple-line graph to show weekly fares for each city type.

### Resources
Data Source: city_data.csv, ride_data.csv 
Software: Python 3.7.6, Jupyter Notebook

## Results
### City Type Summary
We began the analysis by merging both data sources into a new DataFrame. The next step was to retrieve the following data:
1. Total rides by city type
2. Total drivers by city type
3. Total fares by city type

The process we followed to get this information was using the **groupby()** function and the **sum()** or **count()** function

![groupby](https://user-images.githubusercontent.com/22451540/151674929-a29c308c-f1eb-45bd-88ec-55155234b3d2.PNG)
*Fig 1. Using the groupby() function.*

Once we had this information we continued by retrieving the averages fares per ride and per driver for each city type. For this process we simply divided the total fares by the total rides or total drivers information that was analyzed earlier.

The following summary showcases how the rides, fares and drivers is distributed along the different city types.

![pyber_summary](https://user-images.githubusercontent.com/22451540/151674783-95a1dc1b-c00f-4d51-8bd1-6689eb0be5e4.PNG)
*Fig 2. PyBer Summary DataFrame*

From this, we can see how th urban cities hold the majority of the rides (1,625), drivers (2,405) and fares ($39,854.38). However they have the lowest averages fares per ride ($24.53) and per rider ($16.57). This means that the user pays less for the service, but the drivers get less money for their work. Rural cities, on the other hand have a total of 125 rides and only 78 drivers; this means that they have less fares (compared to urban cities) but each ride has a higher average fare ($34.62) and each driver gets a higher fare per drive ($55.49).

### Weekly fares by city type

The next part of the analysis consisted in using that same merged data frame and summarize the information in a different manner. We used again the groupby function using to variables. This gave us a new framing of the data and helped us visualize the data differently.

![multiplegroupby](https://user-images.githubusercontent.com/22451540/151675293-0b6da840-02e2-44c3-8071-3281703c90ff.PNG)
*Fig 3. Using the groupby() function with multiple variables*

Once we had this framing we reset the index and created a pivot table to display the rides using the dates as index.

![pivotrides](https://user-images.githubusercontent.com/22451540/151675362-d89b0e09-9dc7-4d90-aef4-c25b6ef54e6b.PNG)
*Fig 4. Pivot table with date as index*

In order to get a proper visualization of rides along the different dates, we converted the date index to datetime datatype, and later resample the information by week, to get the sum of fares by week.

![weekly](https://user-images.githubusercontent.com/22451540/151675475-b124c711-8d0e-4a15-9b45-07f5e7c7e186.PNG)
*Fig 5. Resampled DataFrame*

Finally, we plotted the resampled data and got the following result:

![PyBer_fare_summary](https://user-images.githubusercontent.com/22451540/151675518-800451c9-88e3-47d1-814a-5e0d322453ff.png)
*Fig 6. PyBer Fare Summary by week*


## Summary
After the analysis, some disparities between the different city types are apparent. Here are some suggestions to overcome them.
1. Reduce the fare in rural cities
2. Incentivize rides in rural cities by offering added value to the users
3. Offer benefits to drivers in all city types to keep them from searching job opportunities elsewhere
