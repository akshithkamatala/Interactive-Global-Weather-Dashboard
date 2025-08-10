# Interactive Global Weather Dashboard – Power BI

A dynamic, dark-themed **Power BI** dashboard that fetches real-time weather and air quality data for multiple global cities using the **WeatherAPI.com** service.

This dashboard provides **current weather**, **7-day forecast**, **hourly trends**, **sunrise/sunset times**, and **air quality KPIs** with dynamically changing visual indicators.

---

##  Features

### **1. City Overview**
- **City selector** with a button-card layout (Albany, Buffalo, Chicago, …, Paris).
- Displays **current temperature** in °F, weather condition icon, and “Feels Like” temp.
- Auto-updates via **Power BI Service** scheduled refresh.

### **2. Forecast Visuals**
- **7-Day Forecast Strip**: Day names, high/low temps, and condition icons.
- **Trend Line Chart** for average temperature across the week.
- **Chance of Rain** and **Chance of Snow** bar charts.

### **3. Hourly Forecast (Dynamic)**
- **Show/Hide Hourly Forecast** toggle button.
- Line chart of hourly temperature for the selected day.

### **4. Environmental Data**
- **Sunrise/Sunset** times with icons.
- **Air Quality Index (PM10)** gauge with conditional color formatting.
- Additional KPIs:
  - Humidity
  - Wind Speed
  - Visibility
  - UV Index
  - Precipitation

---

## Data Model

**Fact Tables**
- `Master_Current_Weather`
- `Master_Forecast by day_Weather`
- `Master_Forecast by hour_Weather`

**Dimension Table**
- `Locations` (city names, country, coordinates)

**Supporting Tables**
- `_Measures` (DAX measure group)
- `Weather_data_*` (per-city API imports)

**Relationship Key**: `location.name`

---

## Key DAX Measures

| Measure | Purpose |
|---------|---------|
| `Current_Temp_f` | Current temperature in °F |
| `feels_like_f` | Feels-like temperature |
| `Avg_temp_day` | Average daily temp for forecasts |
| `Temp_by_hour` | Hourly forecast temperatures |
| `rain_percentage` | Chance of rain per day |
| `snow_percentage` | Chance of snow per day |
| `AQI Color` | Conditional color code for AQI |
| `AQI Condition text` | Air quality category description |
| `Show_Hourly` | Used for toggle button visibility logic |
| `Last Updated date and time` | Timestamp of API fetch |

---

## Data Source & Refresh

- **Source**: [WeatherAPI.com](https://www.weatherapi.com/)
- **Method**: REST API → Power BI Get Data (Web)
- **Frequency**: Scheduled daily/hourly in Power BI Service
- **Privacy**: API key stored in Power BI parameter (not in repo)

---

## Screenshots

### **City Overview**
![Buffalo Overview](reports/buffalo_overview.png)

### **Hourly Forecast**
![Hourly Forecast](reports/rochester_hourly.png)

---

## 📜 License
MIT
