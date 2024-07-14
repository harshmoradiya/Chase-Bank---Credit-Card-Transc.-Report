Credit Card Transaction Report Dashboard with Power BI - (1)

Welcome to my repository! This project showcases the creation of an advanced credit card transaction report dashboard using Power BI, with data sourced from a PostgreSQL database. The project is divided into two main dashboards: **Credit Card Transaction Report** and **Credit Card Customer Report**. This repository includes all the necessary files, queries, and dashboards to replicate and understand the entire project workflow.

Project Overview:
The objective of this project is to develop a comprehensive and interactive credit card dashboard that offers real-time insights into key performance metrics and trends. This dashboard helps stakeholders monitor and analyze credit card operations effectively, enabling data-driven decision-making.

Project Components:

1. Database Setup and Data Import

   1.1. Creating the PostgreSQL Database:
   - Setup: Begin by creating a PostgreSQL database to store credit card transaction data.
   - Schema Definition: Use SQL queries to define the schema for the `cc_detail` table, which includes fields such as `Client_Num`, `Card_Category`, `Annual_Fees`, and `Total_Trans_Amt`.
      1.2. Importing Data:
   - CSV Files: Import the provided CSV files into the PostgreSQL database. Use the appropriate SQL queries to load data into the `cc_detail` table.
   - Power BI Integration: Connect Power BI Desktop to the PostgreSQL server, import the data, and visualize it within Power BI.

2. Data Processing and Analysis in Power BI

   2.1. Data Cleaning and Preparation:
   - Data Cleaning: Check for and address null or duplicate values. Validate column types to ensure data integrity.
   - DAX Queries: Implement Data Analysis Expressions (DAX) to create calculated columns and measures. Examples include:
     - Customer Age Groups: Create age groups to categorize customers.
     - Income Brackets: Define income ranges for better segmentation.
     - Revenue Calculation: Compute total revenue using a formula:
       sql- Revenue = Annual_Fees + Total_Trans_Amt + Interest_Earned
       
     - Week-over-Week Revenue Change: Calculate the percentage change in revenue from week to week.

   2.2. Advanced DAX Measures:
   - Current Week Revenue:Create a measure to track the revenue for the current week:
     sql
     Current_Week_Revenue = CALCULATE(SUM(Revenue), FILTER(ALL(cc_detail), Week_Num_2 = MAX(Week_Num_2)))
     
   - Week-over-Week Revenue Change: Measure the revenue change between weeks:
   - sql
     Week_Over_Week_Revenue = DIVIDE(Current_Week_Revenue - Previous_Week_Revenue, Previous_Week_Revenue)
     

3. Dashboard Design and Visualization

   3.1. Designing the Credit Card Transaction Report Dashboard:
   - Text and Titles: Add clear titles and text to describe each section of the dashboard.
   - Visualizations:
     - Line and Stacked Column Chart: Show quarterly revenue and total transaction amounts.
     - Stacked Bar Charts: Visualize revenue by different dimensions such as expenditure, education level, job category, card category, and chip usage.
     - Table Visualization: Display key metrics such as card category, revenue, total transaction amount, and interest earned.
     - KPIs: Include key performance indicators for total revenue, transaction count, and interest earned.
   - Interactive Elements:
     - Tree Map: Show data distribution by card category and customer ID.
     - Slicers:Include slicers for gender, card category, and income group to filter the data interactively.

   3.2. Formatting and Presentation:
   - Consistent Formatting:Ensure all visualizations have a consistent color scheme and formatting.
   - User-Friendly Design:Focus on a clean, minimalist design to make the dashboard easy to read and interpret for stakeholders.

4. Repository Contents

   4.1. SQL Queries and Scripts:
   - SQL files for database creation and data import.

   4.2. Power BI Files:
   - Power BI (.pbix) file with all visualizations, DAX queries, and dashboard configurations.

   4.3. Data Files:
   - CSV files used for importing data into PostgreSQL.

How to Use This Repository:

1. Clone or Download the Repository:
   - Access the files via the provided GitHub link.

2. Set Up PostgreSQL:
   - Follow the SQL scripts to create the database and import the data.

3. Load Data into Power BI:
   - Use the Power BI file to connect to the PostgreSQL database and start exploring the visualizations.

4. Explore and Customize:
   - Review and modify the Power BI dashboards and DAX queries as needed to fit specific requirements.

For any questions or additional information, please feel free to connect with me!

