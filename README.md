# Uber Demand-Supply Gap Prediction

Uber, a ride-hailing service, processes millions of trip requests daily worldwide. To maintain service reliability, Uber needs to forecast the supply and demand of drivers and riders at specific times and geographic locations. This forecasting enables Uber to guide drivers towards areas with expected surges in demand, maximizing earnings for drivers and providing consistent pricing for riders. Uber divides cities into non-overlapping square regions, with each day divided into 144 time slots. The aim of this problem is to predict the demand-supply gap for each region and time slot, aiding Uber in making informed decisions to optimize driver utilization and provide reliable service.

## Problem Formulation

Given data for each region and time slot, the goal is to predict the demand-supply gap. The supply-demand gap is the difference between passenger requests and driver acceptances in a specific region and time slot. The input data includes passenger requests, driver acceptances, weather conditions, price, POI information, etc. The output is a matrix of demand-supply gaps for each region and time slot. This problem is formulated as a supervised machine learning task, where past data is used to train a model for predicting the gap in new data.

## Data Understanding and Preparation

The data consists of:

1. **Order Information Table**: Contains order details, including passenger and driver IDs, origin, destination, price, and time.
2. **Region Information Table**: Maps region hashes to region IDs.
3. **POI Information Table**: Describes region attributes, such as the number of facilities.
4. **Weather Information Table**: Provides weather data every 10 minutes, including weather conditions, temperature, and PM2.5 levels.

Data Preparation involves joining order and region information, grouping data into 10-minute slots, and calculating the supply-demand gap for each slot. The final dataset includes timestamps, passenger and driver counts, gap, weather, temperature, and PM2.5.

## Feature Engineering

Features used for model training include:

1. Time: 10-minute time slots.
2. Region: Region where requests and acceptances occur.
3. Passenger count: Number of passengers requesting rides.
4. Driver count: Number of available drivers.
5. Weather: Weather conditions at a specific time and region.
6. Temperature: Temperature at a specific time and region.
7. PM2.5: Air pollution level at a specific time and region.

## Model Selection and Evaluation

1. **Linear Regression Model**: Initial model using region_id as the predictor showed limited accuracy.
2. **Multi Regression Model**: Improved model incorporating timestamp and region_id.
3. **Regression Tree Model**: Utilized decision trees with features like region_id, timestamp, and weather conditions for improved accuracy.

Regression Tree performed best with a MSE of 52.41 and an R-squared value of 0.98. This shows that regression tree captures the trends and patterns in data accuratly.

## Model Optimization 
This involved refining features and data grouping to enhance accuracy. Incorporating region_id significantly improved model accuracy, allowing for more precise predictions and better operational decisions.



## Contributors

- Shahwaiz Memon
- Eisha Rehan

