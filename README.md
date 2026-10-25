# Creditcard_Financial_Dashboard
Credit Card Financial Dashboard (Power BI)

An interactive two-page Power BI dashboard on credit card transactions and customers, built on a PostgreSQL database with DAX measures for revenue, segmentation and growth.

Project objective

To give stakeholders an interactive view of credit card revenue, interest, transactions and customer segments, filterable by year, quarter, month and week, so they can monitor performance, spot trends and act on them quickly.

The dashboard answers questions such as:

Which cards, channels and spend types drive revenue?
Which customer segments (age, income, state) are most valuable?
How is revenue trending across quarters, months and years?
What is in this repo
Folder / file	Description
Credit_Card_PowerBI_Project.pptx / .pdf	11-slide project presentation (objective, SQL loading, data model, DAX, dashboards, insights)
project_major.pbix	Power BI report file
dashboards/	PDF exports of the two report pages (Transaction report, Customer report)
sql/	PostgreSQL script that creates the tables and loads the CSV data
data/	Source CSV files (credit_card.csv, customer.csv, plus the week-53 additions cc_add.csv, cust_add.csv)
Tools

PostgreSQL, Power BI Desktop, DAX

Data model
cc_details: card and transaction data (10,108 rows)
cust_details: customer demographics (10,108 rows), one-to-one with cc_details on client_num
Date_Table: calendar table created in DAX, one-to-many to cc_details
DAX highlights
Calculated columns: Revenue, week_num2, AgeGroup, Income_Group
Calculated table: Date_Table (CALENDAR + ADDCOLUMNS)
Measures: TotalRevenue, Current_Week_Revenue, Previous_week_revenue, WoW_growth%, MoM_Growth%, YoY_Growth%
Key findings
Total revenue 55.3M, interest 7.8M, 656K transactions, 10,108 customers
Blue and Silver cards generate about 93.5% of revenue
Card swipes lead the channels at 35M; online transactions add only 3M
Male customers contribute 54.6% of revenue and female customers 45.4%
How to reproduce
Create the database and tables, then load the CSVs using the script in sql/ (update the file paths in the COPY commands to match your machine).
Open project_major.pbix in Power BI Desktop and point the data source at your PostgreSQL database.
Refresh the data.
