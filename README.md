# Real-Time-Data-Processing-System-for-Weather-Monitoring-with-Rollups-and-Aggregates

## Overview
This weather monitoring system retrieves live weather data for major cities in India using the OpenWeatherMap API. It processes, stores, and analyzes the data to generate daily weather summaries, visualize temperature trends, and trigger alerts based on defined thresholds. The system operates in a scheduled manner, fetching data every five minutes and generating visualizations to display temperature summaries for each city.

## Key Components

### Cities Monitored:
The system retrieves weather data for the following major cities in India:
* `Delhi`
* `Mumbai`
* `Chennai`
* `Bangalore`
* `Kolkata`
* `Hyderabad`

### Attributes Collected:

For each city, the following attributes are fetched from the OpenWeatherMap API:
* `city`: Name of the city
* `main`: Dominant weather condition (e.g., Clear, Rain, Cloudy)
* `temp`: Current temperature in Celsius
* `feels_like`: Perceived temperature in Celsius
* `humidity`: Humidity percentage
* `wind_speed`: Wind speed in meters per second
* `timestamp`: Timestamp of the weather data in human-readable format

### Libraries Used:

* `requests` : For making HTTP requests to fetch weather data.
* `sqlite3`: For storing weather data in a local SQLite database.
* `time, schedule`: For managing time and scheduling tasks.
* `datetime`: For handling date and time formatting.
* `unittest`: For writing and executing test cases.
* `matplotlib, pandas`: For data visualization and manipulation.

### Database Management:

A SQLite database (weather_data.db) is used to store daily weather summaries, including:
Attributes in the Database:
* `date`: Date of the summary
* `city`: Name of the city
* `avg_temp`: Average temperature for the day
* `max_temp`: Maximum temperature for the day
* `min_temp`: Minimum temperature for the day
* `dominant_condition`: Most frequent weather condition for the day

### Data Processing:

Weather data is fetched and processed for each city in the list (CITIES).
Daily summaries are calculated, including average, maximum, and minimum temperatures, as well as the most frequent weather condition.
Alerts:

The system includes functionality to check for threshold conditions, triggering alerts if the temperature exceeds a defined threshold (e.g., 35°C).
Visualization:

The daily temperature summaries are visualized using Matplotlib, showing trends for average, maximum, and minimum temperatures over time.
Scheduling:

The system is designed to run scheduled tasks, fetching live data every five minutes. After fetching data, it prints the latest weather conditions and visualizes the daily summaries for each city.

### Main Functions
* `fetch_weather_data(city)`: Retrieves weather data for a specified city from the OpenWeatherMap API.
* `process_weather_data()`: Collects weather data for all specified cities and stores it for further processing.
* `calculate_daily_summary()`: Computes average, maximum, and minimum temperatures for each city and stores the results in the database.
* `store_daily_summary(...)`: Inserts daily weather summary data into the SQLite database.
* `plot_daily_summary(city)`: Visualizes the daily temperature trends for a specified city using Matplotlib.
* `check_thresholds()`: Checks for temperature thresholds and triggers alerts when conditions are met.
* `run_scheduled_tasks()`: Manages the scheduling of data retrieval and summary generation, running for a predefined duration.

### Conclusion
The weather monitoring system effectively integrates multiple components to provide a comprehensive overview of current weather conditions across major cities in India. By leveraging real-time data from the OpenWeatherMap API, it processes and stores relevant weather information, generating insightful daily summaries and visualizations. The inclusion of alert mechanisms for temperature thresholds ensures that critical weather conditions are promptly identified, enhancing the system's usability for both casual users and decision-makers. Overall, this weather monitoring solution offers a robust and efficient way to track and analyze weather patterns, facilitating better planning and response to varying weather conditions.
