# Location Assessment Tool for Aritzia Stores

This project includes several Python scripts that analyze different factors for evaluating the suitability of potential retail store locations for Aritzia and its brands (TNA, Babaton, Wilfred). The analysis incorporates accessibility, competition, safety, customer traffic, and technology infrastructure. This project integrates HTML, CSS, JavaScript, and AJAX on the front end, with a Flask server handling the back end to provide a seamless and dynamic user experience. Below is a description of each main python script and its functionality. 

---

## Table of Contents

1. [airport_accessibility.py](#airport_accessibilitypy)
2. [nearby_public_bus_stops.py](#nearby_public_bus_stopspy)
3. [crimerate_data_clean.py + gather_crime_rates.py](#crimerate_data_cleanpy--gather_crime_ratespy)
4. [nearest_emergency_locations.py](#nearest_emergency_locationspy)
5. [community_ammenities.py](#community_ammenitiespy)
6. [technology_infrastructure.py](#technology_infrastructurepy)
7. [ai_model.py](#ai_modelpy)
8. [get_demographic_data.py](#get_demographic_datapy)
9. [find_competitors.py](#find_competitorspy)
10. [foot_traffic_density.py](#foot_traffic_densitypy)

---

### 1. **airport_accessibility.py**

This Python script evaluates the accessibility of a location based on proximity to the nearest airport and estimated driving times. It utilizes the Google Maps API to calculate the nearest airport within a 50-kilometer radius from the input coordinates and estimates driving times to the airport at different times of the day. This helps determine the logistical convenience for setting up a warehouse or retail facility.

**Key Features**:
- Finds the nearest airport within a 50 km radius.
- Calculates estimated driving times at four different times: 1, 4, 7, and 9 hours from the current time in Eastern Standard Time (EST).
- Provides detailed information on driving distance and ETAs.

**Example Usage**:
```python
airport_accessibility.get_accessibility(latitude, longitude)
```

---

### 2. **nearby_public_bus_stops.py**

This script utilizes the Google Maps API to identify public bus stops within a 1.7-kilometer radius of the provided coordinates. It also calculates the walking distance from the input location to the nearest bus stops. This helps assess the accessibility of a potential location by public transportation.

**Key Features**:
- Identifies bus stops within a 1.7 km radius.
- Calculates walking distances to each bus stop.

**Example Usage**:
```python
nearby_public_bus_stops.get_nearby_bus_stops(latitude, longitude)
```

---

### 3. **crimerate_data_clean.py + gather_crime_rates.py**

These scripts gather and clean crime rate data for a specific location based on coordinates. The neighborhood is identified through reverse geocoding, and the script retrieves crime data for that neighborhood. It calculates the total number of reported crimes and the crime rate per 100,000 people.

**Key Features**:
- Reverse geocodes coordinates to find the neighborhood.
- Filters and calculates crime rate data for the neighborhood.
- Returns crime-related statistics such as total crimes and crime rate per 100,000 people.

**Example Usage**:
```python
crimerate_data_clean.get_crime_data(latitude, longitude)
```

---

### 4. **nearest_emergency_locations.py**

This script finds the nearest emergency services (hospitals, fire stations, and police stations) to the specified coordinates. It calculates distances and durations using the Google Maps API and the Haversine formula.

**Key Features**:
- Identifies nearby hospitals, fire stations, and police stations.
- Calculates driving distances and durations to each service.

**Example Usage**:
```python
nearest_emergency_locations.get_nearest_services(latitude, longitude)
```

---

### 5. **community_ammenities.py**

This script uses the Yelp and Google Maps APIs to identify nearby hotels and restaurants, providing data on their ratings, distance from the coordinates, and estimated driving duration. It evaluates the quality and accessibility of nearby amenities.

**Key Features**:
- Finds top-rated hotels and restaurants near the given coordinates.
- Retrieves information about the name, rating, and distance.
- Calculates the driving duration to each location.

**Example Usage**:
```python
community_ammenities.get_nearby_amenities(latitude, longitude)
```

---

### 6. **technology_infrastructure.py**

This script assesses the technology infrastructure of a location, evaluating internet service providers (ISPs) and the urbanization level. It uses the Speedtest library to find the closest ISPs and the Google Maps Geocoding API to assess the urbanization level.

**Key Features**:
- Identifies ISPs available near the location.
- Assesses urbanization level based on geocoded location.
- Computes a technology infrastructure score based on these factors.

**Example Usage**:
```python
technology_infrastructure.assess_technology_infrastructure(latitude, longitude)
```

---

### 7. **ai_model.py**

This Python script utilizes OpenAI’s API to analyze data points related to crime rate, bus stops, competitors, and foot traffic density, generating an overall suitability score for a retail store location. The model evaluates the factors and provides a recommendation on whether the location is suitable for opening a store.

**Key Features**:
- Analyzes various location data points (crime, competitors, foot traffic).
- Generates a suitability score and provides a recommendation.
- Offers insights into how to compete with existing competitors.

**Example Usage**:
```python
ai_model.run_model()
```

---

### 8. **get_demographic_data.py**

This script retrieves demographic data for a given location, including the population density based on the geographic coordinates. It uses the Google Maps API to determine the city and province, then loads population density data from a CSV file.

**Key Features**:
- Determines the city and province from coordinates using the Google Maps API.
- Retrieves population density data for the specified region.

**Example Usage**:
```python
get_demographic_data.main(geocoding_api_key, latitude, longitude, population_density_file)
```

---

### 9. **find_competitors.py**

This script identifies nearby competitors, such as clothing stores, within a specified radius from the provided coordinates. It uses the Google Maps API to search for competitor stores and calculate walking distances to each store.

**Key Features**:
- Finds nearby competitors within a given radius.
- Calculates walking distance from the input location to each competitor store.

**Example Usage**:
```python
find_competitors.find_competitors(latitude, longitude)
```

---

### 10. **foot_traffic_density.py**

This script calculates foot traffic density by analyzing the number of relevant establishments within a specified radius, such as shopping malls, airports, train stations, and restaurants. The higher the number of relevant establishments, the higher the potential foot traffic density.

**Key Features**:
- Analyzes the number and type of establishments in the area.
- Returns a foot traffic density score based on the concentration of relevant businesses.

**Example Usage**:
```python
foot_traffic_density.get_establishment_count(latitude, longitude)
```

---

## Requirements

- **Google Maps API**: For location data and calculating distances.
- **Yelp API**: For identifying nearby restaurants and hotels.
- **Speedtest Library**: For assessing internet speed and service providers.
- **OpenAI API**: For AI-driven analysis and recommendations.

You will need to replace API keys with your own in the scripts where specified.

---

## Conclusion

This suite of scripts is designed to comprehensively assess the suitability of a location for Aritzia and its brands, helping the team make data-driven decisions about where to open new retail stores.
