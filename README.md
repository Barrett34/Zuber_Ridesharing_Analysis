# Zuber_Ridesharing_Analysis
In this project, I conducted an exploratory and statistical analysis to find patterns from the multiple datasets from Zuber, a ridesharing company in Chicago, and from parsing data from [Zuber Data](https://practicum-content.s3.us-west-1.amazonaws.com/data-analyst-eng/moved_chicago_weather_2017.html). After data cleanup, I tested the following hypothesis:

Duration of rides from the Loop to O'Hare International Airport changes on rainy Saturdays.

# Data Description
A database with info on taxi rides in Chicago:

`neighborhoods table`: data on city neighborhoods

- name: name of the neighborhood
- neighborhood_id: neighborhood code

`cabs table`: data on taxis

- cab_id: vehicle code
- vehicle_id: the vehicle's technical ID
- company_name: the company that owns the vehicle

`trips table`: data on rides

- trip_id: ride code
- cab_id: code of the vehicle operating the ride
- start_ts: date and time of the beginning of the ride (time rounded to the hour)
- end_ts: date and time of the end of the ride (time rounded to the hour)
- duration_seconds: ride duration in seconds
- distance_miles: ride distance in miles
- pickup_location_id: pickup neighborhood code
- dropoff_location_id: dropoff neighborhood code
- weather_records table: data on weather

`record_id`: weather record code
- ts: record date and time (time rounded to the hour)
- temperature: temperature when the record was taken
- description: brief description of weather conditions, e.g. "light rain" or "scattered clouds"


# Conclusion
After conducting our EDA and SDA on the data that we obtained we discovered many useful insights.

From our Company and their Number of Trips dataframe we discovered that the top company was easily Flash Cab. They recorded the highest amount of trips at 19558 trips. I would recommend that Zuber does further research to see what is making Flash Cab attract customers.

From our Dropoff Location dataframe, we discovered that the Loop neighborhood was the most popular to be dropped off at. Zuber should consider having a high amount of drivers in the Loop location for a high amount of trips to be made for future customers.

From our Loop to Ohare dataset we found that from our statistical summary the mean time that it took to complete trips on rainy days was higher than trips on days with good weather conditions. The two-sided statistical t-test showed that we need to reject the null hypothesis being the average duration of rides from the Loop to O'Hare International Airport does not change on rainy Saturdays. We ran the ttest with our two samples of data from rainy days and good weather condition days with an alpha = .05, and the p-value returned a very small value (1.33 ^ -11). Therefore Zuber should prepare to plan for longer trips on rainy Saturdays.
