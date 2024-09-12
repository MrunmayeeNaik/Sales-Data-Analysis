# Sales-Data-Analysis 
Sales Data Analysis project involves examining sales data to uncover insights and identify patterns.In this project, MySQL Workbench was used to analyse data and was linked to Power BI.  Implemented a few PowerBI queries and, in the end, produced an interactive dashboard to monitor the company's sales and provide business insights. The sales team was able to demonstrate a 10% cost reduction in total expenditure by making better decisions with the dashboard's assistance.

## Problem Statement
Atliq Hardware is a company that supplies computer hardwares and peripheral manufacturer to many clients across the country. The Sales Director of Atliq Hardware faces challenge in tracking the sales in this dynamically growing market and get insights of his business across the states.
## Project Planning 
The project is planned according to the AIMS grid which has 4 components
1. **Purpose** :
   To unlock sales insights that aren't visible for the sales team, to make decisions and automate them to reduce manual time spent in data gathering.
2. **Stakeholders** :
   The stakeholders are Sales Director and Analytics team.
3. **End Result** :
   An automated dashboard providing quick & latest sales insights in order to support data driven decision making process.
4. **Success Criteria** :
   Dashboard uncovering sales order insights with latest data available and Sales team able to make better decisions.

## Database 
* The sales database consists of 5 tables namely customers, date, markets,products and transaction.
* The customer table has fields named customer code , customer names and customer type and date table has date,year,month_name and date_yy_mmm.
* Market table consists of market code,markets name, zone and Product table has fields product code ,product type.
* The transaction table has fields named as product code,customer code,market code,order date,sales qty,sales amount and currency.

## Tools Used 
1. **My SQL Workbench** : Performed data cleaning and analysis using SQL queries like joins and used aggregate functions.
2. **Power BI** : To create an interactive dashboard for tracking sales.

## Key Steps in Project
1. **Data Analysis**
Used MySQL Workbench to performed data analysis and understand the data.
* Performed Inner join to combine transaction table with date table to track sales at a particular year using below query.

'SELECT sales.transactions.*,sales.date.* FROM sales.transaction INNER JOIN sales.date ON sales.transaction.order_date=sales.date.date WHERE sales.date.year=2017;'

* Used Aggregate functions to summarize and analyze the sales data shown in below query.

'SELECT COUNT(*) FROM sales.transactions;' 

'SELECT SUM(transactions.sales.amount) FROM transactions INNER JOIN date ON transaction.order_date=date.date WHERE sales.date.year=2017 AND transactions.market_code="Mark001";'

2.**Data Transformation and Loading Power BI**
* The data was loaded in PowerBI and created a Data Model where connections were established between tables.
* Further used PowerBI query to transform data by filtering rows and added a custom column for converting the currency of USD to INR using below formula:

'=Table.AddColumn(#"Filtered Rows" , "norm_amount" , each if [currency] ="USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount] , type any)'

3.**Dashboard Building**
* Created base measures for sales amount to track Revenue which was 984.81 M and sales quantity was 2 M.
* Identified Top 5 Customers and Top 5 Products with respect to year.
* Line chart was included for identifying the revenue trend.
