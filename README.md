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
|![Input](input_example.png) | ![Output](output_example.png) |


| Column | Description |
|-------|---------------------------|
| station |	The same station ID or name as input.|
| dt_hour |	The corresponding hour of prediction.|
| y | The actual observed trip count (ground truth).|
| y_pred | The predicted trip count estimated by the Linear Regression model.|


[bike Indego data](https://www.rideindego.com/about/data/)
