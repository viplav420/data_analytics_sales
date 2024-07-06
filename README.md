Python Operations 

Import Libraries: Import the kaggle library.
Download Dataset: Use the Kaggle API to download the "retail-orders" dataset, specifically the orders.csv file.
Extract File: Extract the contents of the orders.csv.zip file.
Read Data: Read the orders.csv file into a pandas DataFrame and handle null values (replace 'Not Available' and 'unknown' with NaN).
Inspect Data: Display the unique values in the 'Ship Mode' column.
Rename Columns : Code comments indicating renaming columns to lowercase and replacing spaces with underscores.
Derive New Columns: Calculate the profit as the difference between sale_price and cost_price.
Convert Data Type: Convert the 'order_date' column from object type to datetime type.
Drop Columns: Drop the 'list_price', 'cost_price', and 'discount_percent' columns.
Connect to SQL Server: Create an SQLAlchemy engine to connect to a SQL Server instance.
Load Data into SQL Server: Load the DataFrame into a SQL Server table named 'df_orders' using the 'append' option.Import Libraries: Import the kaggle library.

SQL Questions

1)Which are the top 10 highest revenue generating products?

2)What are the top 5 highest selling products in each region?

3)How does month-over-month growth comparison for 2022 and 2023 sales look like? (e.g., Jan 2022 vs Jan 2023)

4)For each category, which month had the highest sales?

5)Which sub-category had the highest growth by profit in 2023 compared to 2022?
