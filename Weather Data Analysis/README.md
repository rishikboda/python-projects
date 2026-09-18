# 🌦️ Weather Data Analysis using Python

A Python-based weather data analysis project that uses the **Open-Meteo API** to retrieve weather information for a selected city, analyzes the temperature data using **Pandas**, and creates a temperature visualization using **Matplotlib**.

## 📌 Features

- 🌍 Accepts city and state as user input
- 📍 Finds the geographical coordinates (latitude and longitude) of the city
- 🌐 Retrieves weather data using the Open-Meteo API
- 📊 Processes weather data using Pandas
- 🌡️ Calculates average daily temperature
- 📈 Creates a temperature graph
- 💾 Saves the weather data as a CSV file
- 🖼️ Saves the generated graph as an image

## 🛠️ Technologies Used

- **Python 3**
- **Requests** – to access APIs
- **Pandas** – for data processing and analysis
- **Matplotlib** – for data visualization
- **Open-Meteo API** – for weather data
- **Datetime** – for calculating dates
- **OS** – for creating the data directory

## 🔄 How the Project Works

The program follows these steps:

```text
User enters city
       ↓
Geocoding API
       ↓
Get latitude & longitude
       ↓
Open-Meteo Weather API
       ↓
Retrieve temperature data
       ↓
Create Pandas DataFrame
       ↓
Calculate average temperature
       ↓
Create temperature graph
       ↓
Save graph + CSV data
🌍 1. Get City Coordinates

The program asks the user for the city and state:

city = input("enter the location of the city")
state = input("enter the location of the state")

The Open-Meteo Geocoding API is then used to find the latitude and longitude of the city.

geo_url = f"https://geocoding-api.open-meteo.com/v1/search?name={city}&count=1"

The coordinates are extracted from the API response:

lat = geo_response["results"][0]["latitude"]
lon = geo_response["results"][0]["longitude"]
🌡️ 2. Retrieve Weather Data

The program calculates the date range and requests daily minimum and maximum temperatures from Open-Meteo.

The weather data includes:

Date
Maximum temperature
Minimum temperature
📊 3. Data Processing with Pandas

The API response is converted into a Pandas DataFrame:

df = pd.DataFrame(
    {
        "date": daily_data["time"],
        "max_temp": daily_data["temperature_2m_max"],
        "min_temp": daily_data["temperature_2m_min"],
    }
)

The project then calculates the average temperature:

df["avg_temp"] = (df["max_temp"] + df["min_temp"]) / 2
📈 4. Data Visualization

Matplotlib is used to create a graph containing:

Maximum temperature
Minimum temperature
Average temperature
plt.plot(df["date"], df["max_temp"], marker="o", label="max Temp")
plt.plot(df["date"], df["min_temp"], marker="o", label="Min Temp")
plt.plot(df["date"], df["avg_temp"], marker="o", label="avg temp")

The graph is saved as:

weather report.png
💾 5. Save Data to CSV

The program creates a data folder if it doesn't already exist:

if not os.path.exists("data"):
    os.makedirs("data")

The processed weather data is then saved as:

data/paris_weather.csv

The CSV contains:

Column	Description
date	Date of the weather data
max_temp	Maximum temperature
min_temp	Minimum temperature
avg_temp	Average temperature
📂 Project Structure
python projects basic/
│
├── mini_atm.py
├── weather_api.py
├── README.md
├── weather report.png
│
└── data/
    └── paris_weather.csv
⚙️ Requirements

Install the required Python libraries:

pip install requests pandas matplotlib
▶️ How to Run

Run the Python program:

python weather_api.py

The program will ask:

enter the location of the city:
enter the location of the state:

Enter the required city and state.

The program will then:

Find the city's coordinates.
Retrieve weather information.
Display the weather data.
Calculate average temperatures.
Generate a graph.
Save the graph.
Save the data as a CSV file.
📸 Output

The program generates a temperature graph showing:

Maximum Temperature
Minimum Temperature
Average Temperature

The graph is saved as:

weather report.png
📚 Python Concepts Learned

This project helped me practice:

API requests
JSON data
User input
Variables
Functions from Python libraries
Pandas DataFrames
Data analysis
Data visualization
Date and time manipulation
File and directory handling
CSV file creation
Exception-aware API workflows
🚀 Future Improvements

Possible improvements for this project:

Add proper error handling for invalid cities
Handle API failures
Use the state input when searching for cities
Allow the user to select the number of days
Add rainfall information
Add humidity information
Add wind speed
Add weather conditions
Create a GUI
Build a web application
Store data for multiple cities
Compare weather between different cities
🎯 Learning Objective

The main objective of this project is to learn how to retrieve real-world data from an API, process the data using Pandas, visualize it using Matplotlib, and store the results in a CSV file.

👨‍💻 Author

Rishik

B.Tech Student
Python Data Analysis Project


### ⚠️ One important correction in your code

Your code says:

```python
week_ago = today - timedelta(days=7)

So you're requesting approximately 7 days of historical/date-range data, but your graph title says:

plt.title(f"weather report of {city} past 10 days")

Those don't match.

I'd change the title to:

plt.title(f"Weather report of {city} - Past 7 Days")

Also, your program asks for:

state = input(...)

but currently doesn't actually use state in the API request. That's not a serious problem for a beginner project, but it's something you can improve in the next version.

And one more thing: your CSV filename is always:

paris_weather.csv

even when the user enters another city. A better version would automatically create something like:

rajkot_weather.csv
mumbai_weather.csv
delhi_weather.csv
