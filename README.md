# Credit-Card-Financial-Analysis
# 🚀 Credit Card Analysis – SQL & Power BI
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

---
## 📊 Power BI Dashboard Features

The dashboard is composed of two primary reports, each providing unique insights into the credit card business.

## 📌 Business Insights

 🔁Transaction Report

-  Revenue Drivers: The "Blue" card category generates the highest revenue and transaction volume, but it also has the highest customer acquisition cost, suggesting it's the primary product.

-  Spending Patterns: Customer spending is highest on "Bills" ($14M), followed by "Entertainment" and "Fuel," identifying the most common use cases for the credit card.

-  High-Value Segments: Customers with a "Graduate" level of education and those who are "Self-employed" or "Businessmen" are the top revenue generators for the business.

-  Transaction Method: Transactions made via "Swipe" generate significantly more revenue ($35M) than transactions using a "Chip" or conducted "Online."
  



🎯  Customer Report

-  Geographic Focus: Texas (TX), New York (NY), and California (CA) are the top three states by revenue, highlighting them as key markets.

-  Demographic Profile: The 30-40 age group is the highest contributor to revenue. Furthermore, customers in the "High" salary group contribute the most revenue, though the "Mid" salary group is also a significant contributor.

-  Gender Contribution: While revenue fluctuates over the year, female customers generate more total revenue ($29.6M) than male customers ($25.8M).

- Customer Loyalty & Satisfaction: The Customer Satisfaction Score (CSS) of 3.19 indicates a need for deeper analysis into the customer experience to improve satisfaction and loyalty.


