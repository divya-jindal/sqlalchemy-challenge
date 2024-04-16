# SQLAlchemy Challenge

This repository contains the code and files for the SQLAlchemy Challenge, focusing on climate analysis and designing a Flask API based on the developed queries. Everything is in the SurfsUp folder

## Files in SurfsUp folder

- `app.py`: This Python script serves as the backbone for the Flask API, providing endpoints to access various climate data and analysis results.
- 'climate_starter.ipynb': This Jupyter Notebook file serves as a comprehensive guide to analyzing and exploring climate data using Python, SQLAlchemy, Pandas, and Matplotlib.

The Resources folder contains the following files:

- `hawaii.sqlite`: This SQLite database file stores the climate data for the Hawaiian islands. It consists of two tables:

    - `measurements`: Contains the following parameters for each measurement:
        - `station`: Station code where the measurement was recorded.
        - `date`: Date of the measurement.
        - `prcp`: Precipitation amount (in inches).
        - `tobs`: Temperature observation (in Fahrenheit).

    - `stations`: Contains information about weather stations in Hawaii, including:
        - `station`: Station code.
        - `name`: Name of the station.
        - `latitude`: Latitude coordinate of the station.
        - `longitude`: Longitude coordinate of the station.
        - `elevation`: Elevation of the station (in meters).
        
**Important Note**: Ensure the `hawaii.sqlite` database file is located in the Resources folder and that the notebook is correctly configured to connect to it using the SQLAlchemy engine.


# app.py

## Overview

The script is organized into the following sections:

1. **Database Setup**: Connects to the SQLite database `hawaii.sqlite` using SQLAlchemy, reflects the database tables into ORM classes, and creates a session to interact with the database.

2. **Flask Setup**: Initializes the Flask application.

3. **Flask Routes**: Defines several routes to access different climate data endpoints.

## Flask Routes

- **Homepage ("/")**: Provides a welcome message and lists available routes for accessing climate data.

- **Precipitation Endpoint ("/api/v1.0/precipitation")**: Returns the precipitation data for the last year in JSON format. It calculates the date one year ago from the last data point, queries the precipitation data for that period, and returns the results.

- **Stations Endpoint ("/api/v1.0/stations")**: Returns a JSON list of stations available in the dataset. It queries the database to retrieve the list of stations and returns them as JSON.

- **Temperature Observation Endpoint ("/api/v1.0/tobs")**: Returns the temperature observations (TOBS) for the previous year for the most active station in JSON format. It queries the database to retrieve temperature data for the most active station over the last 12 months and returns the results.

- **Temperature Statistics Endpoint ("/api/v1.0/temp/start" and "/api/v1.0/temp/start/end")**: Returns temperature statistics (minimum, average, maximum) for a specified start date or start-end range in JSON format. It accepts start and end date parameters, queries the database to retrieve temperature data within the specified range, calculates the statistics, and returns them as JSON.

## Usage

To use the Flask API:

1. Ensure you have the necessary Python packages installed (`numpy`, `sqlalchemy`, `flask`, `matplotlib`, `pandas`).

2. Run the Flask app by executing `app.py`.

3. Modify the url to your liking.

# climate_starter.ipynb

## Overview

The notebook is structured to guide you through the process of:

1. Connecting to the SQLite database `hawaii.sqlite`.

2. Reflecting the database tables into SQLAlchemy ORM classes.

3. Performing exploratory data analysis on the climate data, including precipitation analysis and station analysis.

4. Visualizing the data using Matplotlib to gain insights into the climate trends.

## Exploratory Data Analysis (EDA)

The EDA section includes the following key steps:

1. Finding the Most Recent Date: Retrieves the most recent date in the dataset to determine the timeframe for analysis.

2. Precipitation Analysis: Calculates the precipitation data for the last 12 months and visualizes it as a time series plot.

3. Station Analysis: Determines the total number of stations in the dataset, identifies the most active stations, and calculates temperature statistics for the most active station.

4. Temperature Observation Analysis: Queries the temperature observations (TOBS) for the most active station over the last 12 months and visualizes the distribution as a histogram.

## Usage

To use the notebook:

1. Ensure you have the necessary Python packages installed (`numpy`, `sqlalchemy`, `flask`, `matplotlib`, `pandas`).

2. Open the notebook in a Jupyter Notebook environment.

3. Execute each cell sequentially to perform the analysis steps outlined above.

4. Review the output and visualizations to gain insights into the climate data.


