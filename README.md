# Credit-Card-Financial-Analysis
#🚀 Credit Card Analysis – SQL & Power BI
![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow?logo=powerbi)
![Status](https://img.shields.io/badge/status-Completed-brightgreen)

---
>**Interactive Power BI dashboard to analyze credit card transaction data and customer behavior using SQL-based financial data**
---
## 📊 Project Overview

- The Credit Card Analysis project leverages SQL for data processing and Power BI for building a comprehensive, interactive dashboard. The primary goal is to provide financial stakeholders with a clear, data-driven view of credit card operations, empowering them to make more informed strategic decisions regarding customer behavior and financial performance.
---

## 🛠️ Tools & Technologies

- 🛢️ SQL Server – Data querying, transformation, and cleaning.

- 📊 Power BI – Dashboard creation and data storytelling.

- 📄 CSV –  Raw transaction and customer data source.

- 🧬 GitHub – Version control and project portfolio.

---


## 🗂️ Source Data

- **Data Source**:: A local SQL Server Database named ccdb.
-  **Access Tool**: SQL Server Management Studio (SSMS).

- **Connection Method**: Power BI connected to SQL Server via native SQL connector (Import Mode).
-  **Data Preparation**: Performed in SSMS using SQL queries to create and populate the following tables:


   -  cc_detail: Contains transaction-level data, including total spend, interest earned, and card details.

   -  cust_detail: Contains customer demographic data, such as age, gender, education, and job.

---
## 🧾Business Problems


The dashboard was developed to meet the following needs:

-  Performance & Profitability Analysis: Understanding the overall financial health of the credit card business by analyzing total revenue, interest, and transaction volume.

- Customer Segmentation: Identifying the most profitable customer segments based on demographics (age, education, salary), spending behavior, and card categories.

- Market & Product Insights: Pinpointing top-performing geographical areas, job types, and expenditure categories to inform strategic marketing and product development.

- Transaction Channel Optimization: Assessing the effectiveness of different transaction methods (e.g., chip vs. online) in generating revenue.


## 🔑 KPI Metrics


| KPI                                  | Description                                   |
|------------------|-----------------------------------------------|
💳 Total Revenue	        | The total revenue generated from all credit card transactions|
💰 Total Interest	        |The total interest earned from all credit card accounts|
💵 Transaction Amount	  |The total monetary value of all processed transactions|
🔢 Transaction Count    |	The total number of transactions processed|
💼 Total Income	       |The total income of all customers in the database|
📈 CSS                  |	A score representing overall Customer Satisfaction|

---
## 🧾Sample sql snippets:


<pre> CREATE DATABASE ccdb;

-- 1. Create cc_detail table

CREATE TABLE cc_detail (
    Client_Num INT,
    Card_Category VARCHAR(20),
    Annual_Fees INT,
    Activation_30_Days INT,
    Customer_Acq_Cost INT,
    Week_Start_Date DATE,
    Week_Num VARCHAR(20),
    Qtr VARCHAR(10),
    current_year INT,
    Credit_Limit DECIMAL(10,2),
    Total_Revolving_Bal INT,
    Total_Trans_Amt INT,
    Total_Trans_Ct INT,
    Avg_Utilization_Ratio DECIMAL(10,3),
    Use_Chip VARCHAR(10),
    Exp_Type VARCHAR(50),
    Interest_Earned DECIMAL(10,3),
    Delinquent_Acc VARCHAR(5)
);


-- 2. Create cc_detail table

CREATE TABLE cust_detail (
    Client_Num INT,
    Customer_Age INT,
    Gender VARCHAR(5),
    Dependent_Count INT,
    Education_Level VARCHAR(50),
    Marital_Status VARCHAR(20),
    State_cd VARCHAR(50),
    Zipcode VARCHAR(20),
    Car_Owner VARCHAR(5),
    House_Owner VARCHAR(5),
    Personal_Loan VARCHAR(5),
    Contact VARCHAR(50),
    Customer_Job VARCHAR(50),
    Income INT,
    Cust_Satisfaction_Score INT
);


-- 3. Copy csv data into SQL (remember to update the file name and file location in below query)

-- copy cc_detail table

COPY cc_detail
FROM 'D:\credit_card.csv' 
DELIMITER ',' 
CSV HEADER;


-- copy cust_detail table

COPY cust_detail
FROM 'D:\customer.csv' 
DELIMITER ',' 
CSV HEADER;





-- copy additional data (week-53) in cc_detail table

COPY cc_detail
FROM 'D:\cc_add.csv' 
DELIMITER ',' 
CSV HEADER;


-- copy additional data (week-53) in cust_detail table (remember to update the file name and file location in below query)

COPY cust_detail
FROM 'D:\cust_add.csv' 
DELIMITER ',' 
CSV HEADER;</pre>

📊 Power BI Dashboard Features
The dashboard is composed of two primary reports, each providing unique insights into the credit card business.

1. Credit Card Transaction Report
This report provides a detailed view of financial performance and transactional behavior.

KPIs: Displays high-level metrics for Total Revenue, Total Interest, Transaction Amount, and Transaction Count.

Qtr Revenue & Transaction Count: A time-series chart that visualizes the performance of revenue and transaction count across different quarters.

Card Category & Revenue Analysis: A table and visuals breaking down revenue, interest earned, and annual fees by card categories (Blue, Silver, Gold, Platinum).

Spending Behavior: Bar charts analyze revenue by Expenditure Type, Education Level, and Customer Job.

Customer Acquisition Cost: A table showing the cost to acquire a customer for each card category.

2. Credit Card Customer Report
This report focuses on customer demographics and their influence on financial metrics.

KPIs: Includes high-level metrics for Total Revenue, Total Interest, Total Income, and a Customer Satisfaction Score (CSS).

Revenue vs. Gender: A line chart comparing revenue trends between male and female customers over time.

Top Customer Demographics: A set of charts that break down revenue by key customer attributes, including Age Group, Salary Group, Dependent Count, Marital Status, and Education Level.

Top 5 States: A bar chart identifying the top five states generating the most revenue.

How To Convert Bank And Credit Card Statements To Excel/CSV This video is relevant as it provides guidance on how to convert bank statements to CSV, which is a key step in data preparation for this project.
