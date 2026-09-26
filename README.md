# 🏨 AtliQ Hospitality Revenue & Performance Analytics Dashboard

## 📊 Project Overview

This project focuses on analyzing hotel booking and revenue data to understand the overall business performance of AtliQ Hospitality.

The project uses **Power BI, Power Query, DAX, and data modeling** to transform raw hospitality booking data into interactive dashboards that help analyze:

- Revenue performance
- Occupancy
- RevPAR
- ADR
- Booking volume
- Realization rate
- Cancellation and no-show behavior
- Property-level performance
- City-level performance
- Room-class performance
- Booking-platform contribution
- Week-over-week trends
- Weekday vs weekend performance
- Customer ratings

The main objective was to convert raw booking data into meaningful business insights that could support hotel management in monitoring performance and identifying areas requiring attention.

---

# 🎯 Business Problem

AtliQ Hospitality has booking and hotel performance data spread across multiple tables containing information about:

- Hotels and properties
- Cities and hotel categories
- Room types
- Customer bookings
- Booking platforms
- Booking status
- Revenue
- Room capacity
- Successful bookings
- Customer ratings
- Dates and day types

Analyzing this information manually can make it difficult for management to quickly understand:

1. How much revenue is being generated?
2. Which properties and cities are performing well?
3. How efficiently is available room capacity being utilized?
4. Which booking platforms generate the most bookings?
5. What percentage of bookings are successfully realized?
6. How do weekday and weekend performances differ?
7. Which properties have high or low occupancy?
8. How are key business KPIs changing over time?

Therefore, an interactive business intelligence solution was required to provide a centralized view of hotel performance.

---

# 🎯 Project Objectives

The main objectives of this project were:

### 1. Build a centralized hospitality performance dashboard

Create an interactive Power BI dashboard that brings important hotel KPIs into a single view.

### 2. Monitor key business KPIs

Track:

- Revenue
- RevPAR
- Occupancy %
- ADR
- Realization %
- DSRN
- DBRN
- DURN
- Total Bookings
- Average Rating
- Cancellation %
- No-Show Rate

### 3. Analyze property performance

Compare individual properties based on:

- Revenue
- Occupancy
- RevPAR
- ADR
- Bookings
- DSRN
- DBRN
- Customer ratings

### 4. Analyze city-level performance

Understand differences in:

- Revenue
- Occupancy
- Average rating

across Mumbai, Bangalore, Hyderabad and Delhi.

### 5. Analyze booking behavior

Understand booking contribution across different booking platforms and room classes.

### 6. Analyze time-based performance

Identify trends across:

- Week
- Month
- Weekday
- Weekend

### 7. Enable interactive business analysis

Provide slicers and filters that allow users to drill into performance by:

- City
- Property
- Hotel class
- Room class
- Booking status
- Booking platform
- Month
- Day type

---

# 🗂️ Dataset

The project uses five main tables.

## Dimension Tables

### `dim_date`

Contains:

- Date
- Month-Year
- Week Number
- Day Type

The dataset covers May, June and July 2022.

### `dim_hotels`

Contains:

- Property ID
- Property Name
- Hotel Category
- City

### `dim_rooms`

Contains:

- Room ID
- Room Class

Room classes include:

- Standard
- Elite
- Premium
- Presidential

## Fact Tables

### `fact_bookings`

Contains individual booking-level information including:

- Booking ID
- Property ID
- Booking Date
- Check-in Date
- Check-out Date
- Number of Guests
- Room Category
- Booking Platform
- Customer Rating
- Booking Status
- Revenue Generated
- Revenue Realized

### `fact_aggregated_bookings`

Contains aggregated room-level information:

- Property ID
- Check-in Date
- Room Category
- Successful Bookings
- Capacity

---

# 🏗️ Data Model

The project follows a dimensional modeling approach with hotel, room and date dimensions connected to booking-related fact tables.

```text
                    ┌──────────────┐
                    │   dim_date   │
                    └──────┬───────┘
                           │
                           │
                           ▼
┌─────────────┐      ┌────────────────┐      ┌─────────────┐
│ dim_hotels  │─────►│ fact_bookings  │◄─────│  dim_rooms  │
└─────────────┘      └────────────────┘      └─────────────┘
       │
       │
       ▼
┌──────────────────────────────┐
│ fact_aggregated_bookings     │
└──────────────────────────────┘
# 📊 Dashboard Pages
### Dashboard 1 — Executive Overview
Focus:
- Overall KPIs
- Revenue
- Occupancy
- RevPAR
- ADR
- Realization
- Property performance
- Weekly trends
- Booking platform analysis
(mock up dashboard_atliq grands.png)
