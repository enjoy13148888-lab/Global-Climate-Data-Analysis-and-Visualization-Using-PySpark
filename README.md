# Global Climate Data Analysis with PySpark

This project uses Python and PySpark to process and analyze the Global Historical Climatology Network (GHCN-Daily) dataset at scale, building an end-to-end data pipeline from raw distributed files to climate insights and visualizations.

## Project Overview

GHCN-Daily contains billions of daily weather observations from stations worldwide, with records from the mid-18th century to the present. Handling this 13+ GB compressed (100+ GB uncompressed) dataset requires distributed processing to avoid memory bottlenecks.

In this project, I built an analytical pipeline that:
* Loads compressed daily files and fixed-width metadata into Spark DataFrames.
* Cleans and integrates station, country, state, and inventory tables into an enriched, unified station-level dataset.
* Runs station-level and daily-level analyses to evaluate network coverage, data quality, and long-term climate patterns.
* Generates time-series and geospatial visualizations for New Zealand temperature trends and global rainfall distribution.

## Tech Stack and Skills

* **Languages:** Python
* **Big Data Framework:** PySpark
* **Data Engineering:** Schema design for fixed-width text parsing, optimized join strategies (broadcast and left-anti joins), data aggregation, and User-Defined Functions (UDFs).
* **Analytics & Visualization:** Time-series smoothing, outlier detection concepts (e.g. IQR/Z-scores), and global choropleth mapping.

## Key Technical Highlights

* **Data Integration:** Built an enriched station table combining location data, network flags, and coverage metrics for core elements (TMAX, TMIN, PRCP, SNOW, SNWD).
* **Distributed Processing:** Executed broadcast joins for small metadata tables to minimize costly data shuffling across the cluster.
* **Data Quality Assurance:** Applied left-anti joins to identify missing station records and validated consistency between metadata and active 2026 daily observations.
* **Geospatial Analysis:** Developed a custom Haversine PySpark UDF to calculate the great-circle distance between weather stations in New Zealand.
* **Visual Insights:** Produced New Zealand temperature time-series charts using yearly smoothing to highlight long-term trends, and mapped 2025 global average daily rainfall using Natural Earth projections.


## How to Use

This repository serves as a portfolio demonstration of processing real-world, large-scale climate data. You can read the final report to understand the pipeline design, or inspect the Jupyter notebooks to see how I handle large datasets, optimize joins, and generate visualizations in a cloud-based Spark environment. This project highlights my ability to design scalable Spark pipelines, diagnose data quality issues, and communicate results through clear visualizations.
