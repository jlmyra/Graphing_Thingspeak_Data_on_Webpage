# ThingSpeak Environmental Dashboard

A high-resolution, interactive web dashboard for monitoring sensor data from ThingSpeak Channel **77784**. This tool is designed to provide a professional-grade interface for visualizing temperature, humidity, and pressure data over custom timeframes.

## 🚀 Key Features

* **High-Density Data:** Retrieves up to **8,000 data points** per request for detailed historical analysis.
* **Smart Averaging:** Automatically switches between raw data (short ranges) and 4-hour averaging (long ranges > 48 hours) to ensure fast loading times.
* **Interactive Controls:**
    * **Timeframe Selection:** Precisely filter data using local "From" and "To" date pickers.
    * **Data Series Toggle:** Show or hide Ambient/Healing Temp, RH, and Pressure on the fly.
    * **Range Slider:** Zoom into specific time segments using the interactive slider below the main chart.
* **Live Monitoring:** A built-in **Auto-Refresh** mode that updates the data every 15 minutes.
* **Professional Reporting:** One-click **Save as PDF** feature optimized for printing, which hides dashboard controls for a clean report.

## 🛠️ How to Use

1.  **Open the Dashboard:** Simply double-click the `.html` file in any modern web browser (Chrome or Firefox recommended).
2.  **Set Your Range:** Use the date pickers to select your start and end times.
3.  **Apply Filter:** Click **"Update Graph"** to fetch the data from the ThingSpeak API.
4.  **Live Updates:** To use as a permanent monitoring station, check the **"Live"** box. The dashboard will count down from 15:00 and refresh automatically.
5.  **Export:** Click **"Save PDF"** to generate a clean, full-page report of the current view.

## 📋 Technical Details

* **Data Source:** ThingSpeak API (Channel 77784)
* **Visualization Engine:** Google Charts (Dashboard & ChartRangeFilter)
* **Dependencies:** Requires an active internet connection to load the Google Charts library and fetch data from ThingSpeak.

---
*Generated for the ThingSpeak Environmental Monitoring Project - December 2025*