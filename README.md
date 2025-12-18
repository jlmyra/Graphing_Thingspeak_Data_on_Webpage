# Graphing_Thingspeak_Data_on_Webpage
This `README.md` provides an overview, setup instructions, and technical documentation for the **ThingSpeak Dynamic Dashboard**. This tool uses the Google Charts API to visualize sensor data from ThingSpeak with high-precision time filtering and dynamic field selection.

---

# ThingSpeak Environmental Dashboard

A high-performance, single-page web dashboard designed to fetch and visualize environmental data from a ThingSpeak channel. It features interactive range sliders, custom date-time inputs, and specialized logic to handle API data limits.

## 🌟 Key Features

* **Real-Time Data Fetching:** Pulls the latest 8,000 data points from ThingSpeak based on your custom "To" date.
* **Dynamic Data Series:** Toggle visibility for five specific fields:
* Ambient Temperature & RH
* Healing Chamber Temperature & RH
* Barometric Pressure


* **Interactive Time Filtering:**
* **Manual Inputs:** Set specific start and end times in local time.
* **Range Slider:** Zoom and pan through the data using the Google Charts `ChartRangeFilter`.


* **Smart Axis Padding:** Automatically pads the data table to ensure the chart axis always extends to your requested "To" date, even if the latest sensor data is delayed.
* **Auto-Synchronization:** Automatically adjusts the "From" input box to match the actual timestamp of the first data point returned by the API.

---

## 🚀 Setup & Installation

This dashboard is built as a portable, single-file HTML solution. No web server is strictly required for local testing, though it is recommended for deployment.

1. **Download the Code:** Copy the final HTML/JavaScript block provided in the conversation.
2. **Save the File:** Save the content as `index.html`.
3. **Open in Browser:** Double-click the file to open it in any modern web browser.

> [!IMPORTANT]
> An active internet connection is required to load the Google Charts library (`gstatic.com`) and to fetch data from the ThingSpeak API.

---

## 🛠 Technical Details

### API Configuration

* **Channel ID:** `77784`
* **Data Averaging:** The code uses `average=14400` (4 hours) to optimize performance for long-range historical views.
* **Data Limit:** Fetches a maximum of `8000` results per request to stay within ThingSpeak API constraints.

### The "Padding" Logic

To prevent the chart from "cutting off" at the last recorded data point (e.g., if the sensor stopped at 12/04 but you want to see the axis up to 12/06), the script performs the following:

1. It compares the user-requested `To` date with the `created_at` timestamp of the very last feed.
2. If the requested date is later, it adds a "null" row to the Google `DataTable` at that exact requested time.
3. This forces the chart's horizontal axis to stretch across the entire desired window.

### Dependencies

* **Google Charts Loader:** `corechart` and `controls` packages.
* **ThingSpeak JSON API:** Used for dynamic data retrieval.

---

## 📊 Data Mapping

| Field | Label |
| --- | --- |
| **Field 3** | Ambient Temperature |
| **Field 4** | Ambient RH |
| **Field 5** | Healing Chamber Temperature |
| **Field 6** | Healing Chamber RH |
| **Field 7** | Barometric Pressure |

---

## 📝 Usage Instructions

1. **Set Your Range:** Enter a start and end date in the "From" and "To" boxes.
2. **Apply Filter:** Click **Apply Filter**. The dashboard will fetch the 8,000 points ending at your "To" time.
3. **Adjust View:** Use the checkboxes to compare specific datasets or use the slider at the bottom to zoom into specific events.

