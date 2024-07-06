# Retail Orders Analysis

## Description
This project analyzes retail order data to generate insights such as the top revenue-generating products, highest-selling products in each region, month-over-month sales growth, and more.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Data Source](#data-source)
- [Features](#features)
  
## Installation

### Prerequisites
- Python 3.x
- Anaconda or similar Python distribution
- SQL Server with the necessary permissions

### Installation Steps

1. **Clone the repository:**
   git clone https://github.com/yourusername/retail-orders-analysis.git
   cd retail-orders-analysis
   
2. **Install the required libraries:**
conda install --yes --file requirements.txt

3. **Set up Kaggle API:**

4. **Run the script:Run the script:**

### Usage   

1. **Donwload the dataset from kaggle**
  import kaggle
  Download dataset
  kaggle datasets download ankitbansal06/retail-orders -f orders.csv#!pip install kaggle

2. **Extract the CSV file from the zip file**
   # Extract file from zip file
import zipfile
zip_ref = zipfile.ZipFile('orders.csv.zip') 
zip_ref.extractall() # Extract file to dir
zip_ref.close() # Close file

3. **Read data from the file and handle null values:**
  import pandas as pd
  df = pd.read_csv('orders.csv', na_values=['Not Available', 'unknown'])
  df['Ship Mode'].unique()

4. **Rename columns (make them lowercase and replace spaces with underscores):**
  df.columns = df.columns.str.lower()
  df.columns = df.columns.str.replace(' ', '_')

5. **Derive new columns for discount, sale price, and profit:**
  df['discount'] = df['list_price'] * df['discount_percent'] * .01
  df['sale_price'] = df['list_price'] - df['discount']
  df['profit'] = df['sale_price'] - df['cost_price']

6. **Convert order date from object data type to datetime:**
  df['order_date'] = pd.to_datetime(df['order_date'], format="%Y-%m-%d")

7. **Drop unnecessary columns:**
  df.drop(columns=['list_price', 'cost_price', 'discount_percent'], inplace=True)

8. **Load the data into SQL Server:**
  import sqlalchemy as sal
  engine = sal.create_engine(r'mssql+pyodbc://viplav\SQLEXPRESS/master?driver=ODBC+DRIVER+17+FOR+SQL+SERVER')
  conn = engine.connect()

9. **Append the data to SQL Server table:**
   df.to_sql('df_orders', con=conn, index=False, if_exists='append')

### Problem Statements

1.Find top 10 highest revenue-generating products.

2.Identify top 5 highest-selling products in each region.

3.Compare month-over-month sales growth for 2022 and 2023.

4.Determine the highest sales month for each category.

5.Analyze sub-category growth by profit in 2023 compared to 2022.
