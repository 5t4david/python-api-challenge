# python-api-challenge
# Python API Homework - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's use Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what I may be thinking: _"Duh. It gets hotter..."_

But how would I **prove** it statistically?

![Equator](Images/equatorsign.png)

### Resources and Procedure

1. New git repository called `python-api-challenge`. **Do not add this homework to an existing repository**.

2. Repository cloned to computer.

3. Directories for both of the  Python API Challenges within local repository named accordingly: **WeatherPy**.

4. Inside the directories are files `WeatherPy.ipynb` and `VacationPy.ipynb`. These are the main scripts to run for each analysis.


## Part I - WeatherPy

Here I created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, I utilizing a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

My first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot I added a sentence or too explaining what the code is and analyzing.

My second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

My final notebook:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Here I used my skills in working with weather data to plan future vacations. I used jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** Remember that any API usage beyond the $200 credit will be charged to my personal account. You can set quotas and limits to my daily requests to be sure I can't be charged. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage my cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.

*I Created a heat map that displays the humidity for every city from the part I of the homework.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find an ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * I dropped any rows that don't contain all three conditions. You want to be sure the weather is ideal.

* Using Google Places API to find the first hotel for each city located within 5000 meters of my coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)

As final considerations:

* I created a new GitHub repository for this project called `API-Challenge` (note the kebab-case). **Do not add to an existing repo**
* I complete my analysis using a Jupyter notebook.
* I used the Matplotlib or Pandas plotting libraries.
* For Part I, I included a written description of three observable trends based on the data.
* I used proper labeling of my plots, including aspects like: Plot Titles (with date of analysis) and Axes Labels.
* For max intensity in the heat map, I tried setting it to the highest humidity found in the data set.

## Hints and Considerations

* I started this assignment by refreshing myself on the [geographic coordinate system](http://desktop.arcgis.com/en/arcmap/10.3/guide-books/map-projections/about-geographic-coordinate-systems.htm).

* Studied the OpenWeatherMap API. Based on my initial study, I should be able to answer  basic questions about the API: Where do I request the API key? Which Weather API in particular will I need? What URL endpoints does it expect? What JSON structure does it respond with? Before I write a line of code, I should be aiming to have a crystal clear understanding of my intended outcome.

* Part of our expectation in this challenge is that I will use critical thinking skills to understand how and why we're recommending the tools we are. What is Citipy for? Why would I use it in conjunction with the OpenWeatherMap API? How would I do so?

* In building my script, I paid attention to the cities I am using in my query pool. Am I getting coverage of the full gamut of latitudes and longitudes? Or are am I simply choosing 500 cities concentrated in one region of the world? Even if I were a geographic genius, simply rattling 500 cities based on my human selection would create a biased dataset. Be thinking of how I should counter this, thus I Considered the full range of latitudes.

* Once I have computed the linear regression for one chart, the process will be similar for all others. As a bonus, I created a function that will create these charts based on different parameters.

* Remember that each coordinate will trigger a separate call to the Google API.

David. A 2021
