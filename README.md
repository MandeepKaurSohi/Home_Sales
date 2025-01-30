# Home Sales Analysis

## Overview

This project utilizes SparkSQL to analyze home sales data. The analysis includes querying key metrics, creating temporary views, partitioning data, caching tables, and measuring query performance. The dataset is retrieved from an AWS S3 bucket and processed using PySpark.

## Technologies Used

Python

PySpark (SparkSQL)

AWS S3

Google Colab

## Instructions

Clone the repository and navigate to the project directory.

Ensure you have Apache Spark and Java installed.

Install required dependencies:

pip install findspark

Run the Home_Sales.ipynb notebook to perform the analysis.

## Tasks and Queries Performed

1. Data Loading

Read home_sales_revised.csv from AWS S3 into a PySpark DataFrame.

Display the first few rows of the dataset.

2. Creating Temporary Table

Create a temporary table named home_sales to facilitate SQL queries.

3. SQL Queries

Average price for a four-bedroom house sold per year (rounded to 2 decimal places).

Average price of homes with 3 bedrooms and 3 bathrooms per year built.

Average price of homes with 3 bedrooms, 3 bathrooms, 2 floors, and ≥ 2,000 sqft per year built.

Average home price per "view" rating (≥ $350,000) with runtime measurement.

4. Performance Optimization

Cache the home_sales temporary table.

Verify caching.

Re-run the query from step 3 using the cached data and measure runtime.

5. Data Partitioning

Partition the dataset by date_built and save it as a Parquet file.

Read the Parquet data and create a temporary table parquet_temp_home.

Run the same query on Parquet data and compare the runtime.

6. Cleanup

Uncache home_sales temporary table and verify its removal.


## Results & Observations

The caching mechanism significantly improves query performance.

Partitioning by date_built enhances efficiency when querying based on home construction year.

Using Parquet format reduces query execution time due to its columnar storage format.
