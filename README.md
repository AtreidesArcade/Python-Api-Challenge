# Python-Api-Challenge

## What's the Weather Like?
## Background

This project has two parts one used an API request, and Python script to visualize the weather date of 500+ cities across the world of varying distance from the equator, and sourced under [**WeatherPy folder**](WeatherPy/). I used [**Python library CitiPy**](https://pypi.python.org/pypi/citipy), the [**OpenWeatherMap API**](https://openweathermap.org/api), and created a model of weather across world cities. The cities dataset found in [**output_data folder**](WeatherPy/output_data/cities.csv) which includes the following columns `City_ID`,`City`,`Cloudines`,`Country`,`Date`, `Humidity`,`Lat`,`Lng`,`Max`,`Temp`,`Wind Speed`. The data analyzed, and displayed on [**WeatherPy jupyter notebook**](WeatherPy/WeatherPy.ipynb), and the results are exported in CSV format [**city_weather_data.csv**](WeatherPy/output_data/cities.csv), and the regression plots in the [**output folder**](WeatherPy/output_data/).

The other project [**VacationPy**](VacationPy/) is used the output data from the previous task [**city_weather_data.csv**](WeatherPy/output_data/cities.csv), and analyze data for future vacations and select hotels. For this part of the analysis I used Google Geocode API, Google Places, and delivered results in [**VacationPy jupyter notebook**](VacationPy/VacationPy.ipynb). The analysis covers humidity heatmap in the cities that sourced from the weather data, and spot the hotels on top of the humidity heatmap. You can look at the images in the output folder for both [**the heatmap**](VacationPy/output_data/Heatmap.png) and [**the hotel heatmap**](VacationPy/output_data/hotel.png,) images.

## Observable Trends and Insights 

* The findings of these analysis showed that there is a higher temperature for cities that found near to the equator (Latitude 0), although when we go farther from the equator towards the north the temperature decreases. The regression analysis shows there is a strong negative correlation between temperature and latitude in the Northern Hemisphere. The correlation between temperature and latitude in the Southern Hemisphere is negative but very weak to conclude.

* The findings from the data, plots, and the regression line in the case of testing if there is a relation between humidity and cloudiness of cities nearer or farther to the equator (latitude 0) doesn't show any significant results. The correlation between humidity and latitude for both northern and southern hemisphere cities is very week, negative correlation, and the result for cloudiness and latitude also very week and negative. Therefore, We can infer that humidity can be fairly distributed in both northern and southern hemisphere cities regardless of their distance from the equator.

* The finding from the analysis of the relationship between wind speed (mph) and latitude showed that the lower wind speed when the cities closer to the equater (latitude 0), and somehow the wind speed increase for the cities farther from the equater. The regression analysis also showed there is a very weak posetive correlation between Wind Speed (mph (%) and Latitude in the Northern Hemisphere cities.

* For the second task VacationPy, I created an exploratory-interactive geospatial heat maps that helps visualize the potential socio-economic value buried inside large datasets.

## <a name="WeatherPy"></a> Part I - WeatherPy

In this part, we created a visualization of the weather of 500+ cities across the world of varying distances from the equator was created. After performing the API call from [**OpenWeatherMap API**](https://openweathermap.org/api) a dataframe was created.

After that a series of scatter plots were created to showcase the following relationships:

## <a name="Scatter_Plotting"></a> Scatter ploting
After generating the data a series of scatter plots were created to showcase the following relationships:

### <a name="(#Latitude_vs._Temperature_Plot"></a>Latitude vs. Temperature Plot
![Latitude vs. Temperature Plot](WeatherPy/output_data/latitude_vs_temperature.png)

This scatter plot showcase the relationship between Latitude at x-axis vs Max Temperature (F) at the y-axis. This result indicates that there is a higher temperature for cities that found near to the equater (Latitude 0),however when you go farther from the equator towrads to the north and south the temprature will decrease.
### <a name="Humidity_(%)_vs._Latitude"></a>Humidity (%) vs. Latitude
![Humidity (%) vs. Latitude](WeatherPy/output_data/latitude_vs_humidity.png)

This scatter plot displayed the relationship between Humidity (%) vs. Latitude. From this result we can infer that humidity is fairly distributed troughout the plot, so we can say that high humidity occer for both cities found farther or near to the equator.

### <a name="#Cloudiness_(%)_vs._Latitude"></a>Cloudiness (%) vs. Latitude
![Cloudiness (%) vs. Latitude](WeatherPy/output_data/latitude_vs_cloudiness.png)

This scatter plot showed that the relationship between the cities cloudness, and latitude. From this result we can tell that the data is evenly distributed, and there is no difference in Cloudiness when the cities farther or nearer to the equater(Latitude 0)


### <a name="#Wind_Speed_(mph)_vs._Latitude"></a>Wind Speed (mph) vs. Latitude

![Wind Speed (mph) vs. Latitude](WeatherPy/output_data/latitude_vs_wind_speed.png)

This scatter plot showed the relationship between wind speed (mph), and latitude. The plot displayed the lower wind speed when the cities closer to the equater (latitude 0) and somehow the wind speed increase for the cities farther from the equater.


A linear regression was conducted on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

### <a name="#Northern_Hemisphere_Temperature_(F)_vs._Latitude"></a> Northern Hemisphere - Temperature (F) vs. Latitude
![Northern Hemisphere - Temperature (F) vs. Latitude](WeatherPy/output_data/Northern_Hemisphere_Max_lat_lin.png)

This plot is a linear regression model between Maximum tempreture and latitude for Northern Hemisphere cities. The result from the data showed that there is a strong, negative correlation between Maximum tempreture and latitude. These means when we go farther away to the north from the equater(latitude 0) the maximum Temperature (F) will decrease. Northern_Hemisphere_Humidity _Latitude_Linear.png

### <a name="#Southern_Hemisphere_Temperature_(F)_vs._Latitude"></a> Southern Hemisphere - Temperature (F) vs. Latitude
![Southern Hemisphere - Temperature (F) vs. Latitude](WeatherPy/output_data/southern_Hemisphere_Max_lat_lin.png)

This plot is a linear regression model between Maximum tempreture and latitude for Southern Hemisphere cities. The result from the data showed that there is a very week negative correlation between Maximum Tempreture and latitude in the Southern Hemisphere cities.

![Northern Hemisphere - Humidity (%) vs. Latitude](WeatherPy/output_data/Northern_Hemisphere_Humidity_Latitude_Linear.png)

This plot is a linear regression model between Humidity (%) and Latitude for Northern Hemisphere cities. The result from the data showed that there is a very week negative correlation between Humidity (%) and Latitude in the Northern Hemisphere cities.

### <a name="Southern_Hemisphere_Humidity_(%)_vs._Latitude"></a> Southern Hemisphere - Humidity (%) vs. Latitude
![Southern Hemisphere - Humidity (%) vs. Latitude](WeatherPy/output_data/southern_humudity_Hemisphere_Max_lat_lin.png)

This plot is a linear regression model between Humidity (%) and Latitude for Southern Hemisphere cities. The result from the data showed that there is a very week, negative correlation between Humidity (%) and Latitude in the Southern Hemisphere cities.

### <a name="Northern_Hemisphere_Cloudiness_(%)_vs._Latitude"></a> Northern Hemisphere - Cloudiness (%) vs. Latitude
![Northern Hemisphere - Cloudiness (%) vs. Latitude](WeatherPy/output_data/Northern_Hemisphere_Cloudiness_Latitude_Linear.png)

This plot is a linear regression model between Cloudiness (%) and Latitude for Northern_Hemisphere cities. The result from the data showed that there is a very week,negative correlation between Cloudiness (%) and Latitude in the Southern Hemisphere cities.

### <a name="Southern_Hemisphere_Cloudiness_(%)_vs._Latitude"></a> Southern Hemisphere - Cloudiness (%) vs. Latitude
![Southern Hemisphere - Cloudiness (%) vs. Latitude](WeatherPy/output_data/Southern_Hemisphere_Cloudiness_Latitude_Linear.png)

This plot is a linear regression model between Cloudiness (%) and for Southern Hemisphere cities. The result from the data showed that there is a very week,negative correlation between Cloudiness (%) and Latitude in the Southern Hemisphere cities.

### <a name="Northern_Hemisphere_Wind_Speed_(mph)_vs._Latitude"></a> Northern Hemisphere - Wind Speed (mph) vs. Latitude
![Northern Hemisphere - Wind Speed (mph) vs. Latitud](WeatherPy/output_data/Northern_Hemisphere_Wind_Speed_Latitude_Lin.png)

This plot is a linear regression model between Wind Speed (mph), and latitude for Northern_Hemisphere cities. The result from the data showed that there is a very week, posetive correlation between Wind Speed (mph (%) and Latitude in the Northern Hemisphere cities.

### <a name="Southern_Hemisphere_Wind Speed_(mph) vs. Latitude"></a> Southern Hemisphere - Wind Speed (mph) vs. Latitude
![Southern Hemisphere - Wind Speed (mph) vs. Latitude](WeatherPy/output_data/Southern_Hemisphere_Wind_Speed_Latitude_Linear_Regression.png)

This plot is a linear regression model between Wind Speed (mph), and latitude for Southern Hemisphere. The result from the data showed that there is a very week, negative correlation between Wind Speed (mph (%) and Latitude in the Northern Hemisphere cities.

### Part II - VacationPy
In this part I used a jupyter-gmaps, and the Google Places API for displaying the maps try running humidity heatmap in the cities that sourced from the weather data, and spot the hotels on top of the humidity heatmap.

If gmaps is not working in your environment try to enable by using this code `jupyter nbextension enable --py gmaps`.

* A heat map that displays the humidity for every city from the part I was created.

  ![heatmap](Images/heatmap.png)

* A new dataFrame was created by narrow down the weather data to find the ideal weather condition.

* Finally a gmap plot is created for hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.
