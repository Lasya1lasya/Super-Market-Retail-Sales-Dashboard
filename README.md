# Super-Market-Retail-Sales-Dashboard

## Dataset 

The dataset is a public Kaggle dataset concerning supermarket sales data in Malaysia from January 1st, 2019 to March 30th, 2019.

The dataset is included as a CSV file in this repository and can also be found at https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales/

The dataset can be used to answer a number of useful questions about customer ratings, most profitable branch locations, most profitable product lines, and most profitable days of the week. 

limitation of the data is that the sales were captured during a relatively short timeframe. A longer timeframe could have offered more information about sales fluctuations during holidays and the different seasons of the year. 

The dataset is also from 2019 and may not reflect current consumer trends.

<img width="1323" height="735" alt="Screenshot 2025-10-18 194833" src="https://github.com/user-attachments/assets/f57cd4dd-5fe6-444a-aeac-b392c7ab5e0a" />
<img width="1311" height="716" alt="Screenshot 2025-10-18 194850" src="https://github.com/user-attachments/assets/de81409d-4043-4164-a9f1-d1413d6c43cb" />
<img width="1292" height="643" alt="Screenshot 2025-10-18 194902" src="https://github.com/user-attachments/assets/45e2bbd9-c240-498c-9fa3-7e0aa450fe49" />




## Overview
A supermarket chain is looking to expand their business. The company leadership team has provided the data team with historical supermarket sales data. Leadership is interested in finding answers to several questions:
1) Number of Transactions by Branches
2) Gross Income by Product Line by Branches
3) Gross Income Changes by Branches
4) Average Customer Ratings,Gross Income by Gender and Payment Methods by Branches
5) Customer Spends Overview(Low,High,Medium Spends By Customers)
6) Average Order Value and Gross Margine Percentages
7) Gross Income by cities and Branches

## Role-Based Security (RLS) Implementation

To protect branch-specific data and control user access, Row-Level Security (RLS) was configured in Power BI.

Role Name	Access Level	Description

SalesManager	Full Access	Can view sales data across all branches.
1) BranchA_Manager	Restricted	Can view data for Branch A only.
2) BranchB_Manager	Restricted	Can view data for Branch B only.
3) BranchC_Manager	Restricted	Can view data for Branch C only.

## Implementation Steps

Created roles in Power BI Desktop → Modeling → Manage Roles.

Added DAX filters to restrict visibility by branch:

1) [Branch] = "A"
2) [Branch] = "B"
3) [Branch] = "C"


Published the dataset to Power BI Service and assigned roles under Dataset → Security.

Tested with “View as Role” to verify restricted access for each branch manager.

## Outcome

Ensured that each branch manager only views their respective sales data.

Enhanced data security, governance, and compliance within Power BI Service.

## Tech Stack

Power BI Desktop → Data modeling & visualization

Power BI Service → Publishing, RLS setup, and online access control

DAX → Measures & KPIs (Gross Margin, Total Income, Transactions)

Excel/CSV → Data source for branch-level sales

## **Insights**

### **1. Branch Performance**

* **Branch A** recorded the **highest number of customer transactions (340)**, followed closely by **Branch B (332)** and **Branch C (328)**.
* Despite fewer transactions, **Branch C achieved the highest gross income (≈5.3K)** — indicating **higher-value purchases per customer**.

### **2. Customer Type Analysis**

* **Members (50.85%)** contributed slightly higher income than **Normal customers (49.15%)**, showing that the **loyalty program is driving better revenue**.

### **3. Product Line Performance**

* **Food and Beverages** and **Fashion Accessories** have the **highest gross margin income** across all branches (≈6.5–6.6%).
* **Health & Beauty** and **Sports & Travel** show **lower profit margins**, suggesting potential areas for promotional offers or price optimization.

### **4. Gender-Based Insights**

* **Female customers (51.98%)** generated more income than **male customers (48.02%)**, showing **stronger purchasing engagement** from female shoppers.

### **5. Customer Ratings**

* The **average customer rating is 7/10**, reflecting **moderate satisfaction**. There is room for improvement through better service quality and offers.

### **6. Payment Method Preferences**

* Payments are **evenly distributed** among **E-wallet (34.5%)**, **Cash (34.4%)**, and **Credit Card (31.1%)**, showing customers use **diverse payment options**.

### **7. Spending Segmentation**

* **Low spenders** form the largest customer group (**37.69%**), followed by **medium spenders (34.39%)** and **high spenders (27.92%)**.
* There’s an opportunity to **upsell low and medium spenders** through personalized promotions.

