# BrewMetrics BI

# 24ADC001 — BrewMetrics Coffee Co. Business Intelligence Solution

A version-controlled Power BI solution for analyzing BrewMetrics Coffee Co. sales data across store formats and cities.

## Project Overview
BrewMetrics Coffee Co. operates Flagship, Kiosk, and Drive-Thru formats across four major cities. This BI solution provides interactive reporting and analytical measures to evaluate revenue growth, seasonal category trends, and city-level performance gaps.

## Data Model (Star Schema)
The data model follows star schema design principles to optimize analytical performance:
- **Fact_Sales**: Contains core transaction records including quantities, unit prices, and sales amounts.
- **Dim_Date**: Date dimension table enabling time-intelligence calculations (Year, Month, Month Name).
- **Dim_City**: Dimension table containing unique city locations.
- **Dim_Product**: Dimension table categorizing items into Coffee, Bakery, and Merchandise.
- **Dim_Store_Format**: Dimension table representing operational store formats (Flagship, Kiosk, Drive-Thru).

## Key Business Insights
1. **Cold Brew Seasonal Spike**: Cold Brew sales experience a distinct seasonal surge during the April–May period before leveling off in June.
2. **City Performance Gap**: Bengaluru consistently outperforms all other three operational cities in total sales volume and overall revenue.
3. **Format Performance**: Flagship stores drive the highest average revenue per transaction compared to Kiosks and Drive-Thrus.