# An Analysis of World Weather Data
## Analysis Overview

The purpose of this project is to help PlanMyTrip travel company analyze and filter out the weather data of each city in the database, in order to find the suitable vacation destination where the weather conditions match with the customers' preference (their preferred temperature range of the destination). By retrieving the specific data through APIs (Application Programming Interface) from OpenWeatherMap and Google Cloud Platform websites, PlanMyTrip App will be able to obtain the desired vacation cities dataset for clients, display the summary of their potential travel itinerary, as well as generate the travel route between the four chosen cities of the trip destinations.


## Resources
+ **Programming Language:** Python3
+ **Software:** Jupyter Notebook
+ **Library:** Pandas, NumPy, citypy, requests, gmaps
+ **API:**
	+ OpenWeatherMap API
	+ Google Directions API

## Folders Description
> Note: the `config.py` file that contains the API keys is not included in any folder.

### 1. Weather_Database:
+ Code: `Weather_Database.ipynb`
+ The csv file `WeatherPy_Database.csv` contains 703 cities with their weather data. The cities are obtained using citipy module to find the nearest cities from 2000 random latitudes and longitudes. The weather data of each city is retrieved from OpenWeatherMap API.
+ Outline of the `city_data_df` dataframe 

<img src= https://github.com/asama-w/World_Weather_Analysis/blob/main/Additional%20Images/Weater_database_df.png width="70%" height="70%">


### 2. Vacation_Search:
+ Code: `Vacation_Search.ipynb`
+ The `WeatherPy_vacation.csv` contains 242 potential trip destinations based on the customer's input of preferred trip's temperature range with one nearby hotel name for each city. The data is filtered from the randomly generated cities in the mentioned dataframe above. The nearby hotel name for each city is retrieved via the Google Directions API. The desired destinations are displayed with summary description marker on the map using gmaps module.
+ Input minimum temperature for the trip is 70 Fahrenheit.
+ Input maximum temperature for the trip is 90 Fahrenheit.
+ Outline of the `clean_hotel_df` dataframe

<img src= https://github.com/asama-w/World_Weather_Analysis/blob/main/Additional%20Images/Potential_destination_df.png width="70%" height="70%">

***Potential trip destinations when the customer's preferred temperature range is between 70 - 90 Fahrenheit, displayed with description markers.***

<img src= https://github.com/asama-w/World_Weather_Analysis/blob/main/Vacation_Search/WeatherPy_vacation_map.png width="80%" height="80%">

### 3. Vacation_Itinerary:
+ Code: `Vacation_Itinerary.ipynb`
+ The travel route of four cities, chosen from the WeatherPy_vacation.csv file is generated and displayed with the description markers using gmaps module. The travel mode is set as driving. 
+ Outline of the `itinerary_df` dataframe

<img src= https://github.com/asama-w/World_Weather_Analysis/blob/main/Additional%20Images/Four_destination_df.png width="80%" height="80%">

***Travel route between four destinations by driving (same start and end destination)***

<img src= https://github.com/asama-w/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map.png width="80%" height="80%">

***Four chosen travel destinations with description markers***

<img src= https://github.com/asama-w/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map_markers.png width="80%" height="80%">
