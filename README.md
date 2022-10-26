# Unit 6 Homework: What's the Weather Like?
2
3
## Background
4
5
Whether financial, political, or social&mdash;data's true power rests in its ability to answer questions definitively. So, let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"
6
7
Now, we know what you may be thinking: _"Duh. It gets hotter ..."_
8
9
But, if pressed, how would you **prove** it?
10
11
### Before You Begin
12
13
1. Create a new repository for this project called `python-api-challenge`. **Do not add this homework to an existing repository**.
14
15
2. Clone the new repository to your computer.
16
17
3. Inside your local Git repository, create a directory for both of the Python challenges. Use a folder name that corresponds to the challenges, such as **WeatherPy**.
18
19
4. Inside the folder you just created, add new files called `WeatherPy.ipynb` and `VacationPy.ipynb`. These will be the main scripts to run for each analysis.
20
21
5. Push the above changes to GitHub.
22
23
24
### Adding a .gitignore File
25
26
We don't want the `api_keys.py` file containing the API key to be exposed to the public on GitHub; this would mean anyone could copy and use our API key, possibly incurring charges.
27
28
When we type `git status` in the command line, we can see all the untracked files that we have created so far.
29
30
If we only wanted to add the `WeatherPy.ipynb` file to GitHub, we could type `git add WeatherPy.ipynb`. However, every time we want to add a new file or update current files to the repository, we would have to add each file individually, which is time-consuming and cumbersome. Instead, we can add the files that we don't want to track to the `.gitignore` file.
31
32
Before we add our files to GitHub, let's add `api_keys.py` to the `.gitignore` file. Use the following instructions:
33
34
1. Open your `python-api-challenge` GitHub folder in VS Code.
35
36
2. Open the `.gitignore` file, and on the first line, type the following code:
37
38
```python
39
# Adding config.py file.
40
api_keys.py
41
```
42
43
3. While the `.gitignore` file is open, add the `API_practice.ipynb` and `random_numbers.ipynb` files and save the file.
44
45
4. In the command line, type `git status` and press Enter. The output should indicate that the `.gitignore` file has been modified and the `WeatherPy.ipynb` file is untracked.
46
47
5. Use `git add`, `git commit`, and `git push` to commit the modifications to `.gitignore` and the `WeatherPy.ipynb` file to GitHub.
48
49
On GitHub, the only new file you should find is the `WeatherPy.ipynb` file.
50
51
52
## Part 1: WeatherPy
53
54
In this section, you'll create a Python script to visualize the weather of 500+ cities of varying distance from the equator. To do so, you'll use a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and your problem-solving skills to create a representative model of weather across cities.
55
56
The first requirement is to create a series of scatter plots to showcase the following relationships:
57
58
* Temperature (F) vs. Latitude
59
* Humidity (%) vs. Latitude
60
* Cloudiness (%) vs. Latitude
61
* Wind Speed (mph) vs. Latitude
62
63
After each plot, add a sentence or two explaining what the code is analyzing.
64
65
The second requirement is to compute the linear regression for each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):
66
67
* Northern Hemisphere - Temperature (F) vs. Latitude
68
* Southern Hemisphere - Temperature (F) vs. Latitude
69
* Northern Hemisphere - Humidity (%) vs. Latitude
70
* Southern Hemisphere - Humidity (%) vs. Latitude
71
* Northern Hemisphere - Cloudiness (%) vs. Latitude
72
* Southern Hemisphere - Cloudiness (%) vs. Latitude
73
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
74
* Southern Hemisphere - Wind Speed (mph) vs. Latitude
75
76
After each pair of plots, explain what the linear regression is modeling. For example, describe any relationships that you notice and any other findings you may have.
77
78
Your final notebook must:
79
80
* Randomly select **at least** 500 unique (non-repeated) cities based on latitude and longitude.
81
* Perform a weather check on each of the cities using a series of successive API calls.
82
* Include a print log of each city as it's being processed, with the city number and city name.
83
* Save a CSV of all retrieved data and a PNG image for each scatter plot.
84
85
### Part 2: VacationPy
86
87
Now, let's use your skills working with weather data to plan future vacations. Use Jupyter-gmaps and the Google Places API for this part of the assignment.
88
89
* **Note:** Remember that any API usage beyond the $200 credit will be charged to your personal account. You can set quotas and limits to your daily requests to be sure you can't be charged. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.
90
91
* **Note:** If you are having trouble displaying the maps, run `jupyter nbextension enable --py gmaps` in your environment and then retry.
92
93
To complete this part of the assignment, you will need to do the following:
94
95
* Create a heat map that displays the humidity for every city from Part 1, as in the following image:
96
97
  ![heatmap](Images/heatmap.png)
98
99
* Narrow down the DataFrame to find your ideal weather condition. For example:
100
101
  * A max temperature lower than 80 degrees but higher than 70.
102
103
  * Wind speed less than 10 mph.
104
105
  * Zero cloudiness.
106
107
  * Drop any rows that don't satisfy all three conditions. You want to be sure the weather is ideal.
108
109
  * **Note:** Feel free to adjust your specifications, but make sure to limit the number of rows returned by your API requests to a reasonable number.
110
111
* Use Google Places API to find the first hotel for each city located within 5,000 meters of your coordinates.
112
113
* Plot the hotels on top of the humidity heatmap, with each pin containing the **Hotel Name**, **City**, and **Country**, as in the following image:
114
115
  ![hotel map](Images/hotel_map.png)
116
117
As final considerations:
118
119
* You must complete your analysis using a Jupyter notebook.
120
* You must use the Matplotlib or Pandas plotting libraries.
121
* For Part 1, you must include a written description of three observable trends based on the data.
122
* For Part 2, you must take a screenshot of the heatmap that you create and include it in your submission.
123
* Your plots must include labeling aspects like plot title (with date of analysis) and axis labels.
124
* For max intensity in the heatmap, try setting it to the highest humidity found in the dataset.
125

