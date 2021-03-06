# What's the Weather Like?

## Background

The purpose of this project is to answer the below questions:
* "What's the weather like as we approach the equator?" 
* "Which cities in the world are currently best for vacation based on given weather criteria like temperature, humidity, wind speed, cloudiness?" 
* "Given ideal city locations found in the last question, are there any hotels available for booking?"

## Weather Analysis

[Python script](WeatherPy/WeatherPy.ipynb) has been created to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, I utilized a [citipy library](https://pypi.python.org/pypi/citipy) and the [OpenWeatherMap API](https://openweathermap.org/api).

### The final notebook:
* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### A series of scatter plots to showcase the following relationships:
<table>
  <tr>
      <td> 
        <img src="WeatherPy\output_data\fig2.png" width="80%" height="80%">
      </td> 
      <td> 
        <img src="WeatherPy\output_data\fig3.png" width="80%" height="80%">
      </td> 
  </tr>
  <tr>
      <td> 
        <img src="WeatherPy\output_data\fig1.png" width="80%" height="80%">
      </td> 
      <td> 
        <img src="WeatherPy\output_data\fig4.png" width="80%" height="80%">
      </td> 
  </tr>
</table>

### Linear regression on each relationship:
<table>
  <tr>
    <th>Relationship</th>
    <th>Northern Hemisphere</th>
    <th>Southern Hemisphere</th>
  </tr>
  <tr>
    <td>Temperature (F) vs. Latitude</td>
    <td> 
      <img src="WeatherPy\output_data\fig5.png" width="80%" height="80%"> 
    </td>
    <td>
      <img src="WeatherPy\output_data\fig6.png" width="80%" height="80%"> 
    </td>
  </tr>
  <tr>
    <td>Humidity (%) vs. Latitude</td>
    <td>
      <img src="WeatherPy\output_data\fig7.png" width="80%" height="80%"> 
    </td>
    <td>
      <img src="WeatherPy\output_data\fig8.png" width="80%" height="80%"> 
    </td>
  </tr>
  <tr>
    <td>Cloudiness (%) vs. Latitude</td>
    <td>
      <img src="WeatherPy\output_data\fig9.png" width="80%" height="80%"> 
    </td>
    <td>
      <img src="WeatherPy\output_data\fig10.png" width="80%" height="80%"> 
    </td>
  </tr>
  <tr>
    <td>Wind Speed (mph) vs. Latitude</td>
    <td>
      <img src="WeatherPy\output_data\fig9.png" width="80%" height="80%"> 
    </td>
    <td>
      <img src="WeatherPy\output_data\fig10.png" width="80%" height="80%"> 
    </td>
  </tr>
</table>

## Vacation

This task is about working with weather data to plan future vacations. Jupyter-gmaps and the Google Places API was deployed.

The following was completed:

* Create a heat map that displays the humidity for every city previously identified.

* Narrow down the DataFrame to find your ideal weather condition:

  * Temperature is between 20 and 26 degrees Celsius.

  * Wind speed less than 5 mph.

  * Zero cloudiness.

* Using Google Places API to find the first hotel for each city located within 5000 meters of those coordinates.

Finally, the hotels are plotted on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**:
<img src="VacationPy\output_data\211220_1430_ScreenshotHeatmapLocation_.png" >

For details of vacation coding, refer to [python script](VacationPy/VacationPy.ipynb)
* **Note:** if you having trouble viewing the maps when running the notebook, try running `jupyter nbextension enable --py gmaps` in your environment and retry.
