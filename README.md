# Home_Sales
HW22 - Home Sales Analysis README

Overview
In this challenge, you will utilize your knowledge of SparkSQL to analyze home sales data. The objective is to determine key metrics related to home prices based on various criteria, while also practicing the use of temporary views, data partitioning, and caching in Spark.

1.	Import Necessary Libraries => Import the required PySpark SQL functions for this assignment.

2.	Read Data: => Load the home_sales_revised.csv file from the provided AWS S3 bucket into a PySpark DataFrame. We have a small data set with 33287 row and 11 columns.

3.	Create Temporary Table: => Create a temporary table named home_sales.

4.	Run SparkSQL Queries.

5.	Cache Temporary Table: => Cache the table home_sale.

6.	Run Cached Query: => Using the cached data, rerun the last query and it take almost similar runtime 1.084 for the cached table compare to 1.11 of the uncached one.

7.	Partition the data by the "date_built" vs “view”  field on the formatted parquet home sales data. => the data is going to partitioned on date-built and view. this means that any query that uses date_built and view will be optimized.

8.	Create Temporary Tables for Parquet Data: => Create a temporary table for the parquet data.

9.	Run Partitioned Query: => After partitioning by the "date_built" field on the formatted parquet home sales data. It will make a separate location for each of the rows relevant to that group (pre-group data). That makes specific place to get specific data. However, if the query doesn't contain date built, it will make it worse since we have to go to multiple locations to pull this info.

# Bonus: Then we partition on view (group on view), we should expect to see a performance boost. However, it still doen't help and even take more run time 1.44 vs 0.94 (date-built partition) and 1.084 (cached table), 1.11 (uncached table) due to small files in Spark.

10.	Uncache Temporary Tables



