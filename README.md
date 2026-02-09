# DATA-ANALYSIS-ON-PM25-FOR-MILAN-AND-PARIS


---

## 📊 PM2.5 Air Pollution Analysis: Milan vs Paris (2024)

This project analyzes **daily PM2.5 air pollution levels** in **Milan** and **Paris** during **2024**, using data retrieved from the **OpenAQ API**. The goal is to compare pollution patterns, seasonality, and exceedances of the **WHO PM2.5 guideline (25 µg/m³)** between the two cities.

---

## 🔍 Project Overview

The analysis follows a full data pipeline:

1. **Data collection**

   * Query the OpenAQ API for all available PM2.5 monitoring locations in Milan and Paris
   * Retrieve daily PM2.5 measurements for the full year 2024
   * Handle API rate limits using retries and backoff logic

2. **Data cleaning & filtering**

   * Convert timestamps to UTC-aware datetimes
   * Remove duplicates and enforce strict 2024 coverage
   * Evaluate sensor data coverage (number of days per sensor)

3. **Sensor selection strategies**

   * Automatic selection of sensors with **maximum yearly coverage**
   * Optional **manual sensor selection** for controlled comparisons

4. **Aggregation & analysis**

   * City-level daily PM2.5 averages
   * Descriptive statistics by city
   * Identification of WHO guideline exceedance days

5. **Visualization**

   * Daily time series plots
   * Boxplots and histograms
   * WHO threshold exceedance plots
   * 7-day rolling mean trends

---

## 📈 Key Findings

* **Milan consistently shows higher PM2.5 levels** than Paris across the year
* Pollution peaks are **strongest in winter months (Jan–Feb, Nov–Dec)**
* Milan experiences:

  * Higher average concentrations
  * Greater variability
  * More frequent WHO guideline exceedances
* Paris generally maintains **lower and more stable PM2.5 levels**, with occasional short-lived spikes
* Both cities exhibit **clear seasonality**, with cleaner air in spring and early summer

---

## 🧪 Data Source

* **OpenAQ API (v3)**
* Parameter analyzed: **PM2.5 (µg/m³)**
* Time coverage: **January 1 – December 31, 2024**

---

## 🛠️ Tech Stack

* Python
* pandas, numpy
* requests
* matplotlib, seaborn

---

## 📂 Repository Structure (suggested)

```
├── data/               # (optional) exported datasets
├── notebooks/          # Jupyter notebooks
├── figures/            # Generated plots
├── secrets.json        # API key (excluded via .gitignore)
├── README.md
```

---

## ⚠️ Notes & Limitations

* Sensor availability and coverage vary by city
* Some sensors report missing or negative values (handled during cleaning)
* Results depend on sensor selection strategy (automatic vs manual)
* This project is intended for **exploratory and comparative analysis**, not regulatory assessment

---

## 📌 Future Improvements

* Include additional cities
* Incorporate meteorological variables
* Perform spatial analysis of sensor locations
* Extend to multi-year trend comparisons

---

