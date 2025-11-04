# Databricks Delta Lake: Complete Data Engineering Solution

## Project Overview

This project demonstrates an end-to-end data engineering workflow using Databricks and Delta Lake. The goal is to showcase scalable, reliable, and efficient data processing best practices on Databricks, from raw data ingestion to business insights and optimized data storage.

## Objectives

- **Ingest** raw data from Parquet files using SQL.
- **Clean and pre-process** the data to ensure quality and consistency.
- **Enrich the dataset** with engineered features and location information.
- **Perform exploratory data analysis (EDA)** to uncover key business insights using SQL queries and Databricks visualizations.
- **Optimize operations** for performance using Delta Lake features, including partitioning, OPTIMIZE, and ZORDER BY.
- **Export** the final, curated dataset for downstream use in Delta format.

## Technologies Used

- **Databricks SQL:** For distributed data processing, analysis, and visualization.
- **Delta Lake:** For efficient, reliable, and scalable data storage and management.
- **Parquet:** As the file format for initial data ingestion.

## Workflow Steps

### 1. Data Ingestion

Raw taxi trip data is loaded from Parquet files into a Databricks temporary view. Parquet is chosen for its efficiency in big data analytics.

### 2. Data Cleaning

Data quality is ensured by:
- Standardizing column names.
- Dropping irrelevant columns.
- Filtering out records with null or invalid values (e.g., zero or extreme trip distances, negative amounts).

### 3. Feature Engineering

New features are created to add analytical value:
- **Trip duration** and **average speed** are calculated.
- **Trip category** labels trips as short, medium, or long.
- **Time-based features** (hour, day of week, month, weekend/weekday) are extracted for temporal analysis.

### 4. Data Enrichment (Location Lookup)

The dataset is enriched by joining with a location lookup table, adding borough and zone information for both pickup and dropoff points. This enables more granular geographic analysis.

### 5. Exploratory Data Analysis (EDA)

Key patterns and distributions are explored:
- Busiest pickup and dropoff locations.
- Trip distance distribution.
- Hourly demand and demand by day of week.
- Average fare by passenger count.

Visualizations (bar charts, line charts, histograms) are created using Databricks built-in charting options.

### 6. Business Insights

Specific business questions are answered, such as:
- Total revenue per month.
- Average trip distance by day of week.
- Busiest days by earnings.
- Tip percentage differences between weekdays and weekends.
- Trip distribution across NYC boroughs.

### 7. Save and Optimize Final Dataset

The final, enriched dataset is saved in Delta Lake format, partitioned by month for efficient querying. Delta Lake's OPTIMIZE and ZORDER BY features are used to further improve query performance by compacting files and organizing data for fast access.

## Summary of Findings

- Evening rush hour (5–7 PM) is the busiest time for pickups.
- Manhattan dominates both pickups and dropoffs, accounting for the majority of trips.
- Tip percentages are slightly higher on weekends, indicating different travel patterns or passenger behaviors.

---

This project provides a robust template for scalable data engineering on Databricks, leveraging Delta Lake for reliability and performance, and demonstrates how to turn raw data into actionable business insights.
