# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal of this project was to use statistical modeling techniques to explore factors influencing the availability of shared bikes at docking stations across London. The project combined city bike availability data with contextual information from nearby businesses and points of interest (POIs) using the Foursquare Places API, and applied regression and classification models to uncover relationships and patterns.

## Process
### Step 1: Data Collection and Integration
* Retrieved station-level bike availability data from the CityBikes API.
* Fetched nearby restaurants and bars using the Foursquare Places API for each bike station.
* Merged the two datasets to create a combined view of bike stations and surrounding POIs.
### Step 2: Feature Engineering and Aggregation
* Aggregated POI data by station, calculating average distance to POIs and total POI counts.
* Encoded POI categories using one-hot encoding, reducing category cardinality to the top 10 most frequent types.
* Created target variables: one for regression (free_bikes) and one binary target for classification (bike_availability).
### Step 3: Modeling
* Built an Ordinary Least Squares (OLS) regression model to predict the number of available bikes at a station.


## Results
1. Regression Model: The OLS model showed that the number of empty slots, poi_distance, and certain POI categories (like Pubs, Restaurants, and French Restaurants) were significantly associated with the number of available bikes. Adjusted R² was ~0.28, indicating modest explanatory power.
2. API Coverage: The Foursquare API consistently returned POI results for most bike stations, though some POI types were more prevalent than others. The API’s results were sufficient to provide meaningful context for modeling.

## Challenges 
* Encountered API rate limits and latency issues when querying large batches of bike stations and nearby POIs.
* Ensured proper handling of missing or inconsistent POI data.
* Had to manually reduce category cardinality to make one-hot encoding feasible for modeling.
* Faced SQLite syntax issues when exporting the final DataFrame to a database, which required careful debugging.

## Future Goals
* Incorporate time-of-day or day-of-week trends to model temporal bike availability patterns.
* Use more advanced models (e.g., Random Forest, XGBoost) and cross-validation to improve predictive performance.
* Expand POI context to include more detailed business metrics (e.g., popularity, opening hours).
* Visualize results using a web-based dashboard or interactive map.
* Add automated data pipelines for regular API updates.
