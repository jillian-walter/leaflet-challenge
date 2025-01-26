# leaflet-challenge

This challenge utilizes a combination of HTML, JavaScript and CSS to create an interactive visualization of Earthquakes around the world. Data of all earthquakes that have taken place in the last 7 days is sourced from United States Geological Survey (USGS); data is formatted from their site in a JSON format, located at https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php

![image](https://github.com/user-attachments/assets/7319e9bd-1632-4282-92e2-cdfe1fb329ad)


**HTML Creation:**
CSS for styling is defined first in the HTML, using two sources from Leaflet to create the worldwide map and a simple CSS file defining the boundaries of the map on the page (no borders, filling 100% of the height of the page); this is defined below, and can also be found in the static folder of the challenge:

![image](https://github.com/user-attachments/assets/9c19c81d-449a-4f36-a76c-48ca813c87d1)


Next in the HTML, we create a div class that will hold our map on the page, as defined by the CSS styling. We import three Javascript files/libraries into this section to assist with map interactivity, earthquake information and additional features. Otherwise, our HTML site would just lead to a picture of the world.

The two libraries imported to assist with interactivity and mapping are Leaflet (https://unpkg.com/leaflet@1.9.4/dist/leaflet.js) and D3 (https://d3js.org/d3.v7.min.js). The final JSON file is where the majority of interactivity is coded, utilizing data from the USGS site.

**JSON Creation:**
The JSON file contains multiple functions, highlighted below:

- topographMap: Adds detail to the map surrounding area's topographical details (water, mountains, deserts, city information, etc.) using data from Open Street Map (https://www.openstreetmap.org/copyright)
- earthquakeMap: creates a center to the map when the user enters the site based on lat/long coordinates, and provides a variable for future interactivity to be appended to, including the topographical map.
- setStyle: sets the stage for a circle marker to be created at the location of each earthquake, supported by the below
      - setColor: classifies shades of color based on the earthquake depth (green - high to surface; red - deep underground)
      - setRadius: sets the circle marker size based on the magnitude of the earthquake (bigger circle = bigger earthquake)
- d3.JSON: a **d3 funtion**used to read and process the data found on the USGS site by converting it to a JSON format
- L.geoJson: a **Leaflet function** to read and process the geological data
- setPopUp: sets a marker/popup with information on location, magnitude and depth

Once libraries and markers are set, we iterate through the data, applying a circle size, color and descriptor popup to each earthquake's longitude and latitude over the last 7 days.


**Map Highlights:**
Some of the largest earthquakes in the last week at the time of creation (1/26/2025) was a 6.0 earthquake in Yujing, Taiwan; and 5.7 magnitude earthquakes in Papua New Guinea and the Phillipines. There was also over a dozen small-scale earthquakes around the southern border of Puerto Rico.
