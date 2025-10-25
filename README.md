# Customer_behavior-_analysis
Data Analysis on Customer behavior using Python, PostgreSQL and Power BI
Data Analytics Project: From Python to Power BI Dashboard
📄 Overview

This project demonstrates a complete data analytics workflow — from data loading and cleaning in Python to visualization and reporting in Power BI.
The main goal is to explore, clean, and analyze data effectively to extract meaningful insights and build an interactive dashboard.

📊 Dataset

Source: ( Kaggle )

Format: CSV file

Size:  3900 rows × 18 columns)

Description: The dataset contains information such as customer transactions, reviews, purchase amounts, and subscription details.

🛠️ Tools and Technologies

Python (Jupyter Lab) – For data loading, cleaning, and exploratory data analysis (EDA)

Pandas: For data manipulation 

PostgreSQL – For storing and querying cleaned data

Power BI – For building interactive dashboards and reports

🔍 Steps and Workflow
1️⃣ Load the Dataset

Load the raw dataset into Python (Jupyter Lab) using Pandas:

import pandas as pd
df = pd.read_csv('dataset.csv')

2️⃣ Perform Exploratory Data Analysis (EDA)

Checked for missing values and duplicates

Generated summary statistics

Created visualizations to understand data patterns

3️⃣ Data Cleaning

Filled or removed missing values

Converted data types

Renamed columns for consistency

Exported the cleaned dataset to a new CSV file

4️⃣ Load Clean Data into PostgreSQL

Used Python’s sqlalchemy or psycopg2 to connect and insert the cleaned data into PostgreSQL:

from sqlalchemy import create_engine
engine = create_engine('postgresql://username:password@localhost:5432/database_name')
df.to_sql('customer', engine, index=False, if_exists='replace')

5️⃣ Run SQL Queries

Executed SQL queries to analyze and summarize the data:

SELECT item_purchased, 
       ROUND(AVG(review_rating::numeric), 2) AS avg_rating
FROM customer
GROUP BY item_purchased
ORDER BY avg_rating DESC
LIMIT 5;

6️⃣ Build Power BI Dashboard

Connected Power BI to the PostgreSQL database

Created visualizations such as:

Average review ratings by product

Revenue and customer count by subscription status

Top 5 items with discounts applied

Designed an interactive and professional dashboard

📈 Dashboard and Results

Power BI Dashboard: Showcases key metrics and insights

Key Findings:

Identified top-performing products and categories

Observed trends in customer spending and discounts

Highlighted relationships between review ratings and purchase behavior

🚀 How to Run

Clone this repository:

git clone https://github.com/yourusername/your-repo-name.git


Open the Jupyter Notebook in your environment

Run all cells to clean and load data into PostgreSQL

Open Power BI and connect it to your PostgreSQL database

Refresh visuals to view the dashboard
