# Interactive Global Weather Dashboard – Power BI

A dynamic, dark-themed **Power BI** dashboard that fetches real-time weather and air quality data for multiple global cities using the **WeatherAPI.com** service.

This dashboard provides **current weather**, **7-day forecast**, **hourly trends**, **sunrise/sunset times**, and **air quality KPIs** with dynamically changing visual indicators.

---

##  Features

### **1. City Overview**
- **City selector** with a button-card layout (Albany, Buffalo, Chicago, …, Paris).
- Displays **current temperature** in °F, weather condition icon, and “Feels Like” temp.
- Shows the current situation like "partly Cloudy" and keeps dynamically changing 
- Auto-updates via **Power BI Service** scheduled refresh.

### **2. Forecast Visuals**
- **7-Day Forecast Strip**: Day names, high/low temps, and condition icons.
- **Trend Line Chart** for average temperature across the week.
- **Chance of Rain** and **Chance of Snow** bar charts.

### **3. Hourly Forecast (Dynamic)**
- **Show/Hide Hourly Forecast** toggle button.
- Line chart of hourly temperature for the current day.

### **4. Environmental Data**
- **Sunrise/Sunset** times.
- **Air Quality Index (PM10)** gauge with conditional color formatting and one-line description text.
- Additional KPIs:
  - Humidity
  - Wind Speed
  - Visibility
  - Feels Like
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
- `_Measures` (DAX measures created during the project and grouped in one place)
- `Weather_data_*` (per-city API imports)

**Relationship Key**: `location.name`

---

## Data Source & Refresh

- **Source**: [WeatherAPI.com](https://www.weatherapi.com/)
- **Method**: REST API → Power BI Get Data (Web)
- **Frequency**: Scheduled daily/hourly in Power BI Service
- **Privacy**: API key stored in Power BI parameter (not in repo)

---

## Files

- [Power BI Dashboard GIF (`.png`)](https://github.com/akshithkamatala/sales-receivables-prediction/blob/main/Alteryx_files/Workflow_snap.png)
- [Power BI Dashboard Snapshot (`.png`)](https://github.com/akshithkamatala/sales-receivables-prediction/blob/main/Alteryx_files/Workflow_snap.png)
- [Power BI File (`.yxmd`)](https://github.com/akshithkamatala/sales-receivables-prediction/blob/main/Alteryx_files/data_cleaning.yxmd)
