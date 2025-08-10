# Interactive Global Weather Dashboard – Power BI

I built a **dark-themed Power BI dashboard** that pulls in **live weather and air quality data** for a bunch of cities around the world using **WeatherAPI.com**.  

When you open it up, you can see **current weather**, **7-day forecasts**, **hour-by-hour trends**, when the **sun rises and sets**, and even the **air quality index**, all with visuals that actually change depending on the data.

---

##  What’s Inside

### **1. City Overview**
- You can pick a city from these little button-cards (Albany, Buffalo, Chicago, … all the way to Paris).  
- It’ll show you the temperature in °F, an icon for the current condition, and a short line like *“Partly Cloudy”*.  
- And the best part is it updates automatically if you publish it to the Power BI Service.

### **2. Forecast Visuals**
- Up top there’s a **7-day forecast strip** — you see the day names, highs, lows, and a matching weather icon for each.  
- I added a **trend line** so you can see how the temperature changes across the week.  
- Plus, you get **Chance of Rain** and **Chance of Snow** as simple bar charts.

### **3. Hourly Forecast (Dynamic)**
- a **Show/Hide Hourly Forecast** button.  
- Click it and a line chart pops up showing temperatures hour-by-hour for today.

### **4. Environmental Data**
- I’ve got **sunrise and sunset times**.  
- The **Air Quality Index** (PM10) is a gauge with color coding and a quick one-line description so you know if it’s good, moderate, or bad.  
- And a few more quick stats:
  - Humidity  
  - Wind Speed  
  - Visibility  
  - Feels Like  
  - UV Index  
  - Precipitation  

---

## How the Data’s Set Up

I’ve got three main fact tables:
- `Master_Current_Weather`
- `Master_Forecast by day_Weather`
- `Master_Forecast by hour_Weather`

Then there’s a `Locations` table with the city names, countries, and coordinates.  

I also have:
- `_Measures` — all my DAX measures grouped together.
- `Weather_data_*` — these are the raw imports for each city.

They’re all linked together on `location.name`.

---

## Where the Data Comes From

- All of this comes from [WeatherAPI.com](https://www.weatherapi.com/).  
- I connect through **Get Data → Web** in Power BI, hitting the REST API endpoints.  
- It can refresh daily or hourly once you’ve got it on the Power BI Service.  
- And don’t worry — my API key is stored in a parameter, so it’s not hanging around in the repo.

---

## What’s in This Repo

- [**Dashboard GIF**](https://github.com/akshithkamatala/Interactive-Global-Weather-Dashboard/blob/main/Dashboard.gif) — a quick walkthrough of the dashboard in action.  
- [**Dashboard Snapshot**](https://github.com/akshithkamatala/Interactive-Global-Weather-Dashboard/blob/main/Dashboard_snap.png) — just a still image if you want a quick peek.  
- [**Power BI File (.pbix)**](https://github.com/akshithkamatala/Interactive-Global-Weather-Dashboard/blob/main/Weather_Report.pbix) — the whole thing, so you can open it up and play around.  
