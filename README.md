# Bike-Demand-Philly
## Overview
Bike-share systems such as Philadelphia’s Indego rely on accurate demand forecasting to ensure that bikes and docks are optimally distributed across the network. If operators can anticipate demand surges at specific stations, they can proactively redistribute bikes and prevent shortages.

This project aims to predict the number of bike rentals at each Indego station in the next hour based on temporal, spatial, and environmental factors. The goal is to develop a machine learning model that provides short-term demand forecasts to improve operational efficiency and user satisfaction.


### Authors
[Rui Jiang](https://rumron.github.io/)<br>
[LinkedIn](https://www.linkedin.com/in/rui21/)


### Example Input and Output
For the baseline, I implemented a Linear Regression model to predict hourly bike demand at each Indego station.
The dataset was aggregated to the station–hour level, where each record represents the total number of trips starting from one station within a specific hour.

| Input | Output |
|----------------------------|---------------------------|
|![Input](./figures/input_example.png) | ![Output](./figures/output_example.png) |


| Column | Description |
|-------|---------------------------|
| station |	The same station ID or name as input.|
| dt_hour |	The corresponding hour of prediction.|
| y | The actual observed trip count (ground truth).|
| y_pred | The predicted trip count estimated by the Linear Regression model.|


## Data
### [**bike Indego data**](https://www.rideindego.com/about/data/)<br>
**Data Format**<br>
Each .csv file contains data for one quarter of the year. Each file contains the following data points:

**trip_id**: Locally unique integer that identifies the trip<br>
**duration**: Length of trip in minutes<br>
**start_time**: The date/time when the trip began, presented in ISO 8601 format in local time<br>
**end_time**: The date/time when the trip ended, presented in ISO 8601 format in local time<br>
**start_station**: The station ID where the trip originated (for station name and more information on each station see the Station Table)<br>
**start_lat**: The latitude of the station where the trip originated<br>
**start_lon**: The longitude of the station where the trip originated<br>
**end_station**: The station ID where the trip terminated (for station name and more information on each station see the Station Table)<br>
**end_lat**: The latitude of the station where the trip terminated<br>
**end_lon**: The longitude of the station where the trip terminated<br>
**bike_id**: Locally unique integer that identifies the bike<br>
**plan_duration**: The number of days that the plan the passholder is using entitles them to ride; 0 is used for a single ride plan (Walk-up)<br>
**trip_route_category**: “Round Trip” for trips starting and ending at the same station or “One Way” for all other trips<br>
**passholder_type**: The name of the passholder’s plan<br>
**bike_type**: The kind of bike used on the trip, including standard pedal-powered bikes or electric assist bikes

### [**Station Information**](https://www.rideindego.com/wp-content/uploads/2025/10/indego-stations-2025-10-01.csv)<br>
**Data Format**<br>
**Station ID**: Unique integer that identifies the station (this is the same ID used in the Trips and Station Status data)<br>
**Station Name**: The public name of the station. “Virtual Station” is used by staff to check in or check out a bike remotely for a special event or in a situation in which a bike could not otherwise be checked in or out to a station.<br>
**Go live date**: The date that the station was first available<br>
**Status**: “Active” for stations available or “Inactive” for stations that are not available as of the latest update

