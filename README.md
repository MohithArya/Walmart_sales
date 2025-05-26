# Walmart_sales_proj

This project focuses on analyzing Walmart data through a robust pipeline involving data cleaning in Python, seamless integration with a MySQL database, and extensive querying using SQL. The primary goal is to extract meaningful business insights from the sales data.

## Table of Contents

1.  [Project Overview](#project-overview)
2.  [Files Included](#files-included)
3.  [Dataset](#dataset)
4.  [Python Data Processing](#python-data-processing)
5.  [MySQL Database Integration](#mysql-database-integration)
6.  [SQL Business Problem Solving](#sql-business-problem-solving)
7.  [Key Findings and Insights](#key-findings-and-insights)
8.  [Conclusion and Future Work](#conclusion-and-future-work)

## Project Overview <a name="project-overview"></a>

This project undertakes a comprehensive analysis of sales data, starting with raw CSV data. The process involves:
* Loading the dataset into a Pandas DataFrame.
* Performing essential data cleaning steps in Python (handling duplicates, missing values, and data type conversions).
* Establishing a connection to a MySQL database using SQLAlchemy and PyMySQL.
* Loading the cleaned data into a `walmart` table in the MySQL database.
* Executing a series of complex SQL queries to answer specific business questions related to sales performance, customer behavior, and operational efficiency.
* Extracting key insights from the SQL query results.

## Files Included <a name="files-included"></a>

* `walmart.ipynb`: Jupyter Notebook containing Python code for data loading, cleaning, and MySQL database connection and data export.
* `walmart.sql`: SQL script containing DDL (Data Definition Language) for database creation and DML (Data Manipulation Language) for solving various business problems.
* `README.md`: This document, providing an overview and guide to the project.


## Dataset <a name="dataset"></a>

The project utilizes a sales dataset, assumed to be named `Walmart.csv`. This CSV file is expected to contain columns such as `unit_price`, `quantity`, `PAYMENT_METHOD`, `CATEGORY`, `BRANCH`, `RATING`, `CITY`, `TIME`, `DATE`, and potentially `PROFIT_MARGIN`.

## Python Data Processing <a name="python-data-processing"></a>

The `walmart.ipynb` notebook performs the following data processing steps:

1.  **Data Loading**: Reads the `Walmart.csv` file into a Pandas DataFrame.
2.  **Initial Exploration**:
    * Displays the first and last few rows (`df.head()`, `df.tail()`).
    * Checks the DataFrame's dimensions (`df.shape`).
    * Provides descriptive statistics (`df.describe()`).
    * Summarizes DataFrame information including data types and non-null values (`df.info()`).
3.  **Data Cleaning**:
    * **Duplicate Handling**: Identifies and removes duplicate rows from the dataset.
    * **Missing Values**: Identifies and drops rows containing any null values.
    * **Data Type Conversion**: Converts the `unit_price` column from a string (with a '$' symbol) to a float data type.
4.  **Feature Engineering**:
    * Calculates a new `Amount` column by multiplying `unit_price` and `quantity`.

## MySQL Database Integration <a name="mysql-database-integration"></a>

The Python notebook establishes a connection to a MySQL database using SQLAlchemy and PyMySQL. After cleaning and preparing the data, the DataFrame is exported and appended to a table named `walmart` in the `walmart` database on the MySQL server.

## SQL Business Problem Solving <a name="sql-business-problem-solving"></a>

The `Walmart.sql` script contains a series of SQL queries designed to answer specific business questions about the sales data. These queries demonstrate various SQL techniques, including aggregation, ranking functions, date/time manipulation, and joins.

The following business problems are addressed:

1.  **Payment Method Analysis**: Identifies different payment methods and calculates the total number of transactions and items sold for each.
2.  **Category Rating by Branch**: Determines which category received the highest average rating in each branch.
3.  **Busiest Day of the Week**: Identifies the busiest day of the week for each branch based on transaction volume, involving date column conversion and extraction of day names.
4.  **Items Sold by Payment Method**: Calculates the total number of items sold for each payment method.
5.  **Rating Statistics by Category and City**: Computes the average, minimum, and maximum ratings for each product category within each city.
6.  **Profit by Category**: Calculates the total profit for each category and ranks them from highest to lowest (assuming a `PROFIT_MARGIN` column is available or derived).
7.  **Most Frequent Payment Method by Branch**: Determines the most frequently used payment method in each branch.
8.  **Transactions by Shift**: Counts the number of transactions occurring in each shift (Morning, Afternoon, Evening) across different branches, involving time column conversion and case statements.
9.  **Revenue Decrease Analysis**: Identifies branches that experienced the largest decrease in revenue compared to the previous year (specifically comparing 2022 to 2023).

## Key Findings and Insights <a name="key-findings-and-insights"></a>

Through the execution of the SQL queries, the project aims to uncover insights such as:

* The most common payment methods and their contribution to overall sales volume.
* Categories that are highly rated in specific branches, indicating customer satisfaction.
* Peak transaction days for each branch, which can inform staffing and operational planning.
* The overall sales distribution across different payment channels.
* Variations in customer ratings for categories across different cities.
* Top-performing categories in terms of profit.
* Preferred payment methods in individual branches.
* Transaction patterns across different times of the day (shifts).
* Branches facing significant revenue decline, highlighting areas for business intervention.

*(Note: Specific numerical findings and detailed conclusions would be derived by running the SQL queries and analyzing their output.)*

## Conclusion and Future Work <a name="conclusion-and-future-work"></a>

This project successfully demonstrates a robust data analysis workflow, from raw data ingestion and cleaning in Python to structured querying and insight extraction using SQL. The integration of Python for data preparation and MySQL for complex aggregations and reporting provides a powerful framework for business intelligence.

While this project focuses on data cleaning and SQL-based analysis, future enhancements could include:

* **Data Visualization**: Creating interactive dashboards and charts using Python libraries (e.g., Matplotlib, Seaborn, Plotly) to visually represent the key findings and trends.
* **Advanced Analytics**: Implementing more sophisticated statistical analysis or machine learning models (e.g., sales forecasting, customer segmentation).
* **Automated Reporting**: Setting up automated scripts to refresh data and generate reports periodically.
* **Error Handling**: Adding more comprehensive error handling in the Python script for database operations.
