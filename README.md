# RetailPulse: AI-Powered Customer Analytics & Demand Forecasting Platform

## Project Overview

**RetailPulse** is a retail analytics and business intelligence project developed using Microsoft Power BI. It transforms retail sales, customer, product, store, promotion, and inventory data into interactive dashboards that help businesses monitor performance, understand customer behavior, analyze profitability, identify inventory risks, and explore sales trends.

The project uses datasets downloaded from **Kaggle** and organizes the data into a structured analytical model for reporting and visualization.

The primary objective is to demonstrate how data analytics and business intelligence can support data-driven decision-making in the retail industry.

## Project Objectives

- Analyze overall retail sales and business performance.
- Monitor revenue, profit, cost of goods sold, and gross profit margin.
- Identify sales trends across dates, months, and years.
- Understand customer demographics, loyalty segments, and purchasing preferences.
- Compare sales performance across cities, stores, and sales channels.
- Analyze discounts, promotions, and their relationship with sales and profitability.
- Monitor stock availability, reorder thresholds, stockout risks, and slow-moving products.
- Examine transaction patterns and average transaction values.
- Identify high-performing products and product categories.
- Explore historical sales patterns to support demand forecasting and business planning.

## Data Source

The datasets used in this project were downloaded from **Kaggle**.

The data was prepared and organized into multiple tables to support retail sales analysis, customer analytics, inventory monitoring, and interactive reporting.

**Data source:** Kaggle  
**Data processing and visualization tool:** Microsoft Power BI

*Note: The exact Kaggle dataset title, original author, and source URL should be added to the repository once confirmed.*

## Tools and Technologies

- **Microsoft Power BI Desktop** — Interactive dashboards and business intelligence reporting.
- **Power Query** — Data preparation, transformation, validation, and cleaning.
- **DAX (Data Analysis Expressions)** — Calculated measures, business KPIs, and calculated columns.
- **Data Modeling** — Relationships between sales, customer, product, store, promotion, and inventory tables.
- **Kaggle** — Source of the downloaded datasets.
- **GitHub** — Project documentation, version control, and portfolio presentation.

## Dataset Structure

The project uses seven main tables in the Power BI data model.

| Table | Description |
|---|---|
| `fact_sales` | Transaction-level sales data, including date, receipt ID, store ID, SKU, customer ID, quantity, unit price, total value, channel, discount percentage, and promotion ID. |
| `dim_customer` | Customer demographics and preferences, including age, gender, city, loyalty segment, preferred channel, and registration date. |
| `dim_sku_master` | Product information, including SKU name, category, subcategory, unit price, cost price, and brand. |
| `dim_store_master` | Store information, including store name, city, store type, and opening date. |
| `dim_promo` | Promotion details, including promotion name, dates, discount percentage, promotion type, and targeting information. |
| `fact_inventory` | Inventory data, including store ID, SKU ID, stock on hand, reorder point, safety stock, and last restock date. |
| `fact_inventory_flags` | Inventory risk indicators, including stockout risk, slow movers, affected stores, time windows, and notes. |

## Data Preparation and Data Quality

The project included data preparation and validation steps to make the datasets suitable for analysis.

Key activities included:

- Reviewing column names and data types.
- Checking missing values and data completeness.
- Validating positive quantities, unit prices, and sales values.
- Checking discount percentages against the expected 0–100% range.
- Identifying duplicate transaction rows.
- Reviewing customer and product identifiers.
- Validating inventory quantities and replenishment thresholds.
- Examining promotion identifiers and missing promotion values.
- Reviewing inventory risk flags and their associated date fields.
- Preparing tables for use in the Power BI data model.

During validation, 1,434 duplicate rows were identified in the sales transaction data, based on the row counts recorded during the project. Promotion IDs were populated for approximately 18% of sales records, while approximately 82% were empty or missing. These observations were considered during data preparation.

The `fact_sales[total_value]` field represents the final sales amount after discount, which is important when calculating revenue and interpreting promotional activity.

## Data Modeling

The Power BI model connects the sales and inventory fact tables with the relevant customer, product, store, and promotion dimensions.

The model uses active relationships and single-direction filtering for the relationships established during development.

The relationships support analysis across dimensions such as:

- Product category and brand.
- Store and city.
- Customer demographics and loyalty segments.
- Sales channels.
- Inventory and stock risk.
- Promotion attributes.

A structured data model allows measures and visuals to respond to applicable filters and selections.

## DAX Measures and Calculated Columns

DAX was used to create analytical measures and calculated columns for business reporting.

Key measures used throughout the dashboard include:

- **Total Sales** — Sales revenue recorded in the selected reporting context.
- **Total Profit** — Profit calculated using the project's cost and sales logic.
- **Total COGS** — Cost of goods sold.
- **Gross Profit Margin %** — Gross profit expressed as a percentage of sales.
- **Total Transactions** — Transaction count according to the defined measure.
- **Average Transaction Value** — Average sales value per transaction.
- **Total Quantity Sold** — Total units sold.
- **Total Discount Amount** — Estimated discount value based on the discount calculation used in the project.
- **Discounted Transactions** — Number of transactions classified as discounted.
- **Discounted Transactions %** — Percentage of transactions classified as discounted.
- **Average Revenue per Customer** — Average revenue per purchasing customer according to the defined measure.

Additional calculated columns include customer age groups and transaction size categories.

The age groups are classified as Under 20, 20–29, 30–39, 40–49, 50–59, and 60+. Transaction sizes are classified as Small, Medium, and Large using the thresholds defined in the project.

## Dashboard Pages and Features

The RetailPulse Power BI report is organized into 12 analytical pages, with a maximum of six visuals per page.

### 1. Executive Summary
Provides a high-level overview of retail business performance through KPI cards and summary charts. It is designed to help users review key business indicators quickly.

### 2. Sales Trend Analysis
Examines historical sales trends over time, helping users understand changes in revenue and identify patterns across the reporting period.

### 3. Product Performance Analysis
Supports analysis of product performance, sales contribution, and product-level business results.

### 4. Customer Analytics
Includes customer KPIs and visualizations for sales by loyalty segment, customer counts by loyalty segment, average revenue per customer, and revenue comparisons across loyalty groups.

### 5. Regional Sales Analysis
Analyzes sales and profit across cities, compares store types, identifies the top 10 stores by sales, and examines transaction volume and average transaction value by city.

### 6. Inventory & Stock Risk
Monitors total stock on hand, stockout-risk products, stock on hand versus reorder points, products by inventory risk type, stock levels by store, and slow-moving products.

### 7. Sales Channel Analysis
Compares sales, transactions, average transaction value, units sold, total profit, and gross profit margin across sales channels.

### 8. Discount & Promotion Analysis
Examines total discount amount, discounted transactions, discounted transaction percentage, sales by discount percentage, profit by discount percentage, and sales by promotion type.

### 9. Customer Behaviour Analysis
Analyzes customer distribution by gender, age group, and loyalty segment. It also compares sales and average revenue across age groups and examines customer preferences by sales channel.

### 10. Profitability Analysis
Focuses on total profit, cost of goods sold, gross profit margin, profit by product category, profit by city, and gross profit margin by product category.

### 11. Order & Transaction Analysis
Examines total transactions, average transaction value, transactions by transaction size, sales by transaction size, transactions by sales channel, and average transaction value by channel.

### 12. Demand & Sales Forecasting
Combines historical sales trends, monthly sales analysis, annual sales trends, monthly units sold, top 10 products by units sold, and sales by product category. A three-month forecast was also added to the historical sales line chart using Power BI's built-in forecasting feature.

## Interactive Reporting Features

The dashboard was designed to support interactive exploration through:

- KPI cards for key business metrics.
- Bar charts and column charts for comparisons.
- Donut charts for customer distributions.
- Line charts for historical trends and forecasting.
- Date-based filtering.
- Visual interactions and cross-filtering.
- Category, customer, store, and channel comparisons.
- Top 10 product and store analyses.

These features allow users to examine business performance at different levels of detail and explore patterns within the available data.

## Key Business Questions Addressed

RetailPulse is designed to help answer questions such as:

1. How are total sales and profit changing over time?
2. Which cities and stores contribute the most revenue?
3. Which product categories generate the most profit?
4. How does customer loyalty relate to sales performance?
5. Which age groups contribute to retail revenue?
6. Which sales channels generate more transactions and higher average transaction values?
7. How do sales and profit vary across discount levels?
8. Which products are flagged as potential stockout risks?
9. Which products are classified as slow movers?
10. How does current inventory compare with reorder thresholds?
11. Which products have the highest historical unit sales?
12. What historical sales patterns can support demand forecasting?

## Business Value

The project demonstrates how retail data can be transformed into actionable business reporting.

Potential business applications include:

- Monitoring sales performance and profitability.
- Supporting product and category planning.
- Understanding customer segments and purchasing preferences.
- Comparing regional and channel performance.
- Reviewing discount and promotion activity.
- Identifying inventory replenishment concerns.
- Investigating slow-moving products.
- Supporting demand planning using historical sales patterns.

The dashboard supports analysis and decision-making; it does not independently establish causation between discounts, sales, or profit.

## Project Scope and Limitations

RetailPulse is primarily a Power BI analytics and dashboard project.

The current implementation includes data preparation, data modeling, DAX calculations, interactive reporting, inventory risk analysis, and a built-in Power BI sales forecast.

Although the broader project concept includes AI-powered customer analytics, machine learning, automated ETL, and MLOps, these capabilities should be considered future extensions unless separately implemented and documented.

The built-in Power BI forecast is based on historical sales data and should not be interpreted as a guarantee of future performance.

## Future Enhancements

Potential future improvements include:

- Customer segmentation using machine learning.
- Customer churn prediction.
- Advanced demand forecasting using Prophet or other forecasting models.
- Automated data refresh and ETL workflows.
- Inventory optimization and replenishment recommendations.
- Forecast accuracy evaluation.
- Data quality monitoring and automated alerts.
- Deployment of analytical applications using Streamlit.
- Model tracking and monitoring using MLflow.
- Cloud deployment and production-oriented MLOps workflows.

These enhancements would extend the current dashboard into a more comprehensive retail analytics platform.

## Project Outcome

RetailPulse demonstrates practical skills in Power BI, Power Query, DAX, data modeling, data validation, KPI development, and interactive dashboard design.

By combining retail sales, customer, product, store, promotion, and inventory data, the project provides a structured view of retail business performance and demonstrates how business intelligence can support evidence-based decision-making.

## Author

**Akash Ghosh**

Data Analytics | Microsoft Power BI | DAX | Business Intelligence | Retail Analytics

## Acknowledgment

The datasets used in this project were downloaded from Kaggle. Credit for the original data belongs to the respective dataset creator or publisher. Please refer to the original Kaggle dataset page for its specific attribution and licensing terms.
