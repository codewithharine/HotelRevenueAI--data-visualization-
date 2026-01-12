# Hotel Business: Understand and Improve Revenue (Milestone 1)

## 📌 Project Overview
This project is part of **Module 1: Data Modeling and Ingestion**. The goal is to transform raw hotel booking data into a robust **Star Schema** data model using **Power BI**. This foundation enables efficient analysis of revenue, profit, and customer trends.

## 📂 Repository Structure
```text
Hotel_Business_Understand_Improve_Revenue/
 ── Milestone 1/
    ├── Module1_PowerBI.pbix        # Functional Power BI file
    ├── data/
    │   └── Hotel book.csv          # Raw dataset
    ├── screenshots/
    │   ├── data_model.png          # Star Schema view
    │   ├── power_query_steps.png   # Transformation steps
    │   └── visuals.png             # Key insights dashboard
    └── README.md                   # Project documentation

# Hotel Business: Understand and Improve Revenue (Milestone 1)

## 📊 Dataset Description
The dataset (`Hotel book.csv`) contains daily aggregated performance metrics for a hotel, rather than individual transactional bookings.

* **Time Period**: January 2024 to April 2024 (Daily Data).
* **Key Metrics**: Revenue, Occupancy Rate, ADR (Average Daily Rate), Check-ins, Cancellations, and Costs.
* **Attributes**: Guest Country, Market Segment, Booking Channel.

## 🛠️ Methodology & Transformations

### 1. Data Ingestion & Cleaning (Power Query)
* Loaded raw CSV data into Power BI.
* Checked for correct data types (Dates, Decimals for currency).
* **Calculated Profit**: Created a custom column `Profit` = `[Revenue] - [Total_Costs]` (since the raw column was empty/null).

### 2. Calculated Columns
Specific business logic was applied to categorize data:

* **Booking Duration (Avg Length of Stay)**:
    * *Logic*: `If [Checkins] > 0 Then ([Available_Rooms] * [Occupancy_Rate]) / [Checkins] Else 1`
    * *Purpose*: Determines the average days a guest stays.
* **Room Category** (Derived from ADR):
    * **Standard**: ADR < 120
    * **Deluxe**: 120 <= ADR <= 128
    * **Suite**: ADR > 128
* **Stay Type**:
    * **Short**: Duration < 3 days
    * **Medium**: 3 <= Duration <= 7 days
    * **Long**: Duration > 7 days
    * *Observation*: Due to the aggregated nature of the data (high occupancy vs. low check-ins), most records fall under "Long" stays.

### 3. Data Modeling (Star Schema)
The data was normalized into a Star Schema to improve performance and filter context.

* **Fact Table**: `Fact_Bookings`
    * Contains quantitative metrics: Revenue, Profit, Bookings, RevPAR, Occupancy.
    * Contains Foreign Keys: `Date`, `Customer_Key`, `Room_Key`.
* **Dimension Tables**:
    * `Dim_Date`: Date, Month, Weekday, Season, Holiday.
    * `Dim_Customer`: Unique combinations of Guest Type, Country, Channel, and Market Segment.
    * `Dim_Room`: Room Categories (Standard, Deluxe, Suite).

## 📈 Key Visualizations
The Power BI report includes:

* **Revenue vs. Profit Trends**: A line chart tracking financial performance over time.
* **Revenue by Room Category**: Identifying high-value room types (Suites vs. Standard).
* **Geographic Analysis**: Bookings breakdown by `Guest_Country`.
* **KPI Cards**: High-level view of Total Revenue, Total Profit, and Average Occupancy.

## 📝 Key Observations
* **Profitability**: Profit margins track closely with Revenue, but "Suite" rooms generally provide a higher contribution margin.
* **Seasonality**: Distinct trends observed between "Winter" and "Spring" months.
* **Data Structure**: The source data is daily summaries, which requires weighted averages for calculating metrics like "Average Length of Stay" rather than simple row counts.