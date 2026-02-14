# HotelRevAI – AI Driven Revenue Analysis for Hotels

This project focuses on analyzing hotel booking data to understand revenue performance, guest behavior, and future demand using **Power BI**.  
The work is structured into three milestones, each building on the previous one.

---

## 📁 Project Structure

HotelRevenueAI--data-visualization-
├── Milestone 1
├── Milestone 2
├── Milestone 3
├── Milestone 4
└── README.md

---

## 🟢 Milestone 1: Data Modeling and Ingestion

### Objective
To prepare and model hotel booking data for analysis.

### Key Activities
- Loaded hotel booking dataset into Power BI
- Performed basic data cleaning using Power Query
- Designed a **Star Schema** with:
  - Fact Table: Bookings
  - Dimension Tables: Date, Customer, Room, Branch
- Created calculated columns:
  - Booking Duration
  - Room Category
  - Stay Type

### Outcome
A clean, well-structured data model ready for analytical reporting.

---

## 🟢 Milestone 2: Revenue and Guest Analysis

### Objective
To analyze revenue, occupancy, and guest behavior using DAX and interactive visuals.

### Key Metrics (DAX Measures)
- Occupancy %
- Average Daily Rate (ADR)
- Revenue per Available Room (RevPAR)

### Analysis Performed
- Revenue and booking trends (Daily, Monthly, Seasonal)
- Direct vs OTA booking comparison
- Guest analysis by:
  - Nationality
  - Booking source
  - Length of stay
- Guest segmentation:
  - First-time Guests
  - Loyal Guests
  - High Spenders

### Outcome
An interactive dashboard providing actionable insights into hotel performance and guest behavior.

---

## 🟢 Milestone 3: Forecasting and Cancellation Analysis

### Objective
To forecast future demand and analyze cancellations and no-shows.

### Forecasting Approach
- Used historical booking data
- Applied Power BI’s built-in forecasting on net bookings
- Identified trend and seasonal patterns

### Analysis Performed
- Forecast vs actual bookings
- Cancellation rate trend
- No-show analysis
- Booking lead-time distribution

### Key KPIs
- Cancellation Rate %
- No-Show Rate %
- Net Bookings
- Expected Future Demand

### Outcome
A decision-support dashboard highlighting future demand, risk areas, and booking behavior patterns.

---
# Milestone 4 – Revenue Strategy Dashboard

## Pricing Tier Logic
Pricing recommendations were derived by analyzing ADR and seasonal demand. 
High-demand seasons with lower ADR suggest potential price increases, while low-demand periods indicate promotional opportunities.

## Upsell Strategy Identification
Upsell potential was estimated based on occupancy levels and room category performance. 
High occupancy periods indicate opportunities to promote spa, dining, and premium services.

## Seasonal Promotion Insights
- Winter shows peak revenue performance.
- Summer requires promotional pricing strategies.
- Direct booking channels provide higher profitability.

## Key Revenue Improvement Recommendations
- Increase ADR in high-demand seasons.
- Offer bundled services for premium room categories.
- Promote direct booking incentives to reduce OTA dependency.

## Business Impact
The strategy dashboard enables data-driven pricing adjustments, optimized occupancy management, and improved revenue forecasting.

--- 

## 🛠 Tools Used
- Power BI Desktop
- Power Query
- DAX
- Git & GitHub

---

## 📌 Key Learnings
- Designing star schema data models
- Creating business metrics using DAX
- Building interactive dashboards
- Translating historical data into future insights

---

## ✅ Conclusion
This project demonstrates the ability to convert raw hotel booking data into meaningful business insights, supporting revenue optimization and strategic decision-making.

