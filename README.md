# geog458-labs
Lab exercises for GEOG 458: Digital Geography

## Lab 3: Raster Tile Services and Air Quality

### Guided Map — Puget Sound PM2.5

**Purpose:**  
This map shows measured PM2.5 concentrations from monitoring stations in the Puget Sound region and an interpolated surface estimating PM2.5 values between those stations. It allows users to compare measured station values with the spatial pattern estimated using IDW interpolation.

**Study area:**  
Puget Sound, Washington, with emphasis on the Seattle metropolitan area.

**Data sources:**  
- U.S. EPA AirData PM2.5 monitoring data for July 5, 2025  
- Mapbox Studio basemap  
- Monitoring station locations from the supplied GeoJSON data

**Processing:**  
The PM2.5 station data were projected to WGS 84 / UTM Zone 10N in QGIS. An Inverse Distance Weighted (IDW) interpolation was created from the measured PM2.5 values. The raster was styled using a yellow-to-red color ramp and exported as local PNG map tiles using QMetaTiles. The Mapbox Studio basemap was exported separately as another raster tile pyramid. The original WGS84 station points were added as a GeoJSON layer in MapLibre so users can click stations and view measured values.

**Tile export:**  
Both the basemap and PM2.5 raster were exported as 256-pixel PNG tiles with zoom levels 8–12.

**Measurements vs. estimates:**  
The station popups represent actual measured PM2.5 observations. The IDW raster is an estimated surface between monitors and should not be interpreted as measured values or AQI.

### Guided map screenshot

![Puget Sound PM2.5 guided map](images/pm25-map.png)

---

### Independent Map — Puget Sound Ozone

**Purpose:**  
This map shows maximum 8-hour ozone concentrations from EPA monitoring stations and an IDW interpolation estimating ozone concentrations between monitors. The map helps users compare measured ozone values across the Puget Sound region and examine their broader spatial pattern.

**Study area:**  
The Puget Sound region of Washington, including monitoring locations from the Seattle metropolitan area and surrounding counties.

**Data sources:**  
- U.S. EPA AirData daily ozone data for July 5, 2025  
- Mapbox Studio independent basemap  
- EPA ozone monitoring station locations and attributes

**Processing:**  
EPA daily ozone records were filtered to July 5, 2025 and the selected Puget Sound monitoring stations. The station data were projected to WGS 84 / UTM Zone 10N for interpolation. An IDW surface was created from the maximum 8-hour ozone values and styled from dark blue for lower concentrations to yellow for higher concentrations. The ozone raster and the independent Mapbox basemap were exported separately as local PNG tile pyramids using QMetaTiles. The station data were exported as GeoJSON for interactive display and popups in MapLibre.

**Tile export:**  
The independent Mapbox basemap and ozone interpolation were exported as 256-pixel PNG tiles using zoom levels 8–12.

**Measurements vs. estimates:**  
The station points provide measured maximum 8-hour ozone values in parts per million (ppm), along with AQI and station information. The IDW surface estimates ozone concentrations between monitoring stations; the interpolated colors do not represent individual measurements or AQI values.

### Independent map screenshot

![Puget Sound ozone independent map](images/ozone-map.png)

### Interactive features

Both maps include:
- Raster layer visibility controls
- Interactive monitoring station layers
- Station popups showing measured observations
- Matching legends for the interpolated raster surfaces
- Navigation and scale controls