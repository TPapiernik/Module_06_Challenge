# Module 06 Challenge - PlanMyTrip

## Overview

The purpose of this project was to aid the team in the development of the PlanMyTrip App.

The project was divided into Three main segments:

1. Weather Data Collection
2. Creation of a Customer Travel Destinations Map
3. Creation of a Travel Itinerary Map

### Resources

- Data Source(s): User-Generated, OpenWeather Current Weather API, Google Maps Geo-location APIs (Places, Directions)
- Software: Jupyter notebook server 6.3.0, running Python 3.7.10 64-bit
	- Dependencies: citipy, gmaps, matplotlib, numpy, os, pandas, requests


### Data Quality
The feedstock data for this project relies on Commercial Providers at the Back End, namely OpenWeather and Google. A quick examination of the data retrieved reveals no glaring errors or inconsistencies. Some of the results for names of Hotels present in the Travel Destinations Map contain non-Latin Characters. For any rigorous analysis attempted using these data, character sets should be properly applied.


## Weather Data Collection (Weather_Database)

To get a good overall representation of weather across the globe where our customers may be traveling, a test set of 2,000 randomly-generated Latitude and Longitude locations were generated.

The Python citipy Module was used to find the nearest city to each of these locations, yielding 782 randomly-selected cities across the globe.

These cities in turn were correlated to cities having available Current Weather data from OpenWeather. Current Weather was obtained for 713 Cities on July 13, 2021.

To simplify the rest of the App Development, and to facilitate ease of testing, these results were saved locally to disk in CSV Format. This static data file was used as an Input for the remainder of the project.

In a future, live product scenario, the OpenWeather API would be directly mated to the App Front-End for continuously-updating Weather Conditions.


## Customer Travel Destinations Map (Vacation_Search)

Now, the exciting part! Among the 713 potential destinations, our customers are able to specify a preference for Maximum and Minimum preferred temperatures during their vacation. During the testing phase, we have done this for them with a Minimum trip temperature of 75 deg F and Maximum trip temperature of 90 deg F.

Once selected, the Google Maps Places API is consulted to find the Nearest Hotel for each city that meets the criteria. If a Hotel is not found for a given city, it is dropped from the results. In our test case, there were 257 remaining to choose from across the Globe.

These potentials are displayed on a clickable, user-interactive Google Map with Clickable Markers. Upon selection, a brief description is returned including the Hotel Name, City Name, Country, and Current Weather.


## Travel Itinerary Map (Vacation_Itinerary)
