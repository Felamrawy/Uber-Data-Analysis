# 🚗 Uber Trip Data: Exploratory Data Analysis & Dashboard

This project provides a detailed Exploratory Data Analysis (EDA) and an interactive dashboard for Uber trip data. The analysis focuses on travel patterns, trip purposes, mileage efficiency, and identifying temporal trends in business and personal drives.

## 📌 Project Overview
The primary goal is to understand the logistics of Uber drives through data cleaning and visualization. The project identifies key performance indicators (KPIs) such as average mileage, trip durations, and peak travel times.

### Key Research Questions:
* What are the primary purposes for Uber trips (e.g., Meetings, Meals, Customer Visits)?
* How does trip mileage vary between Business and Personal categories?
* What are the peak times of day and days of the week for travel?
* Are there any "illogical" trips in the dataset (e.g., zero duration but high mileage)?

## 📂 Dataset
* **File:** `UberDataset.csv`
* **Size:** 1,156 entries initially, cleaned to 1,154 valid records.
* **Features:** Start Date, End Date, Category (Business/Personal), Start/Stop locations, Miles, and Purpose.

## 🛠️ Data Cleaning & Feature Engineering
* **Handling Missing Values:** Missing "Purpose" entries were filled as "Unknown" to maintain data integrity.
* **Date Standardization:** Handled multiple date formats and converted them into standard datetime objects.
* **Feature Extraction:** Created new features including:
    * `duration`: Total trip time in minutes.
    * `start_day`: Day of the week (Monday-Sunday).
    * `hour`: Hour of departure.
    * `time_of_day`: Categorized into Morning, Afternoon, Evening, and Night.
* **Anomaly Detection:** Identified and flagged 28 illogical trips where speeds were physically impossible (e.g., "inf" speed due to 0-minute duration).

## 📊 Visualizations & Insights
* **Trip Length Distribution:** Box plots comparing Business vs. Personal miles, showing Business trips are more frequent but personal trips can have higher outliers.
* **Average Mileage by Purpose:** Bar charts breaking down average miles per trip based on the specific intent (e.g., Commute, Customer Visit).
* **Time of Day Trends:** Analysis of when trips occur most frequently, helping identify "Afternoon" as a high-volume period for specific purposes.

## 🚀 Interactive Dashboard
The project includes a built-in **Dash** application to explore the data dynamically.
* **Local Host:** `http://127.0.0.1:8054`
* **Features:** * Real-time KPI summaries (Avg Miles, Total Trips, Avg Duration).
    * Interactive Bar and Donut charts for Category and Purpose distribution.
    * Time-series volume trends.

## ⚙️ Installation & Usage
1. **Dependencies:**
   ```bash
   pip install pandas plotly dash dash-bootstrap-components numpy
   ```

2. Open [EDA-UBER.ipynb](./EDA-UBER.ipynb) and run the final cell, or run the script containing the Dash code.

3. Access the dashboard in your browser at: http://127.0.0.1:8054