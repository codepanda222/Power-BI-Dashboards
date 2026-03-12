# 📊 Annual Sales Performance by Branch and Salesperson
### Microsoft Dynamics 365 Business Central Integrated Dashboard

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow?logo=powerbi)
![ERP](https://img.shields.io/badge/Data-Dynamics%20365%20Business%20Central-blue)
![Language](https://img.shields.io/badge/Language-DAX-orange)
![API](https://img.shields.io/badge/Integration-OData%20V4-green)

---

## 🔎 Project Overview

This project delivers an end-to-end Power BI reporting solution built on data extracted from **Microsoft Dynamics 365 Business Central (OData V4 API)**.

The dashboard provides real-time visibility into:

- 📈 Total Sales by Month, Location Code & Salesperson  
- 📦 Top 20 Customers by Branch & Salesperson
- 🔁 Backorders by Salesperson
- 📝 Open quote value by Location and Salesperson
- 📈 Converted quote value by Location and Salesperson
- 🏆 Total Sales by Location code and Salesperson

The objective is to support operational and strategic decision-making across sales, resources and inventory planning.

---

## 🌐 Business Context

This dashboard was developed for a **sales-driven distribution business using Microsoft Dynamics 365 Business Central**.

The organisation manages multiple branches and sales teams, where performance is measured through sales revenue, customer relationships, and quote conversion effectiveness.

Key operational considerations include:

- Monitoring **sales performance across branches and salespeople**
- Identifying **high-value customers and revenue concentration**
- Tracking **backorders that may impact order fulfilment**
- Analysing **quote pipelines and conversion rates to forecast revenue**
- Providing **real-time visibility into sales and operational performance**

The primary challenge was transforming **ERP transactional data from Business Central into a structured analytical model** that supports strategic and operational decision-making.

---

## 🛠 Technology Stack

- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**
- **Microsoft Dynamics 365 Business Central**
- **OData V4 Web Services**
- **Excel (Data Validation & Exploration)**

---

## 🔗 Data Integration Architecture

Power BI connects directly to Business Central via OData endpoints:

```text
https://api.businesscentral.dynamics.com/v2.0/{tenant}/Production/ODataV4/Company('CompanyName')/
```

### 🏢 Tables Integrated

- Sales Header  
- Sales Line  
- Purchase Header  
- Purchase Line  
- Item  
- Vendor  
- Customer  
- Item Ledger Entries  

### 🧠 Key Technical Challenges Resolved

- HTTP 400 errors due to missing Document IDs  
- Relationship modelling between Header and Line tables  
- Handling archived documents  
- Optimising refresh performance  
- Creating efficient data model relationships  

---

## 📊 Dashboard Modules


### Total Sales Analysis
- 📅 Total Sales by Month
- 📍 Sales by Location Code
- 👤 Sales by Salesperson
- 📈 Monthly Sales Trends & Performance

---

### Top Customers Performance
- 📦 Top 20 Customers by Revenue
- 🏢 Customer Sales by Branch
- 👤 Customer Sales by Salesperson
- 📊 Revenue Contribution % by Customer

---

###  Backorders Monitoring
- 🔁 Backorders by Salesperson
- 👤 Backorders by Customer
- 📦 Backorders by Product / Item
- 💰 Outstanding Order Value

---

###  Open Quotes Analysis
- 📝 Open Quote Value by Location
- 👤 Open Quotes by Salesperson
- 💰 Total Outstanding Quote Value
- 📊 Quote Pipeline Overview

---

###  Quote Conversion Performance
- 📈 Converted Quote Value by Location
- 👤 Converted Quotes by Salesperson
- 🔄 Quote-to-Sales Conversion Rate
- 💰 Revenue from Converted Quotes

---

### Location & Salesperson Performance
- 🏆 Total Sales by Location Code
- 👤 Sales by Salesperson
- 📊 Branch-wise Revenue Distribution
- 📈 Salesperson Performance Ranking
---

## 📈 Key DAX Measures

```DAX
Total Sales =
SUM('Sales Line'[Amount])

Total Cost =
SUM('Sales Line'[Cost Amount])

Gross Margin =
[Total Sales] - [Total Cost]

Gross Margin % =
DIVIDE([Gross Margin], [Total Sales], 0)

Backorder Qty =
SUM('Sales Line'[Outstanding Quantity])

Customer Rank =
RANKX(
    ALL(Customer[Customer Name]),
    [Total Sales],
    ,
    DESC
)
```

---

## 🧠 Data Model Design

The model follows a **Star Schema Architecture**:

### Fact Tables
- Sales Line  
- Purchase Line  
- Item Ledger Entries  

### Dimension Tables
- Customer  
- Vendor  
- Item  
- Date  

Relationships were structured to maintain referential integrity and optimise performance.

---

## 📷 Dashboard Preview

### 📈 Sales Overview
![Sales Overview](Annual%20Sales%20Report%20Home.JPG)

---

### 🏆 Top Customers Analysis
![Top Customers](Annual%20Sales%20Report%20Top%20Customers.JPG)

---

### 🔄 Quote Conversion Dashboard
![Quote Conversion](Quote%20Conversion%20Value%20and%20Count.JPG)

---

### 👤 Salesperson Performance
![Salesperson Performance](Salesperson%20Performance%201.JPG)

---

### 📊 Salesperson Performance Details
![Salesperson Performance Details](Salesperson%20Performance%202.JPG)
---

## 📌 Business Insights Generated


### 📈 Sales Performance Trends
- Total sales reached **$77M**, with monthly sales ranging between **$1.5M–$2.8M**.
- Sales show **seasonal fluctuations**, with peaks around mid-year periods.

---

### 📍 Branch Performance
- **Melbourne** is the top-performing branch (~$26M), followed by **Albury (~$18.7M)**.
- Other branches like **Adelaide, Townsville, and Gippsland** contribute moderate revenue.

---

### 👤 Salesperson Performance
- **AWEYMOUTH** and **PWILSON** are the highest revenue-generating salespeople.
- Sales performance is **concentrated among a few top performers**.

---

### 🏆 Customer Revenue Contribution
- **Top 20 customers generate over $12M in revenue**.
- The largest customer contributes **over $1.2M individually**.

---

### 🔁 Backorders Analysis
- Backorders are heavily concentrated under **one salesperson (JTANTI)**.
- Indicates potential **inventory shortages or supply chain delays**.

---

### 📝 Open Quotes Pipeline
- **Melbourne has the highest open quote value**, indicating strong future sales potential.
- **PWILSON leads the quote pipeline** among salespeople.

---

### 📊 Quote Conversion Performance
- Total **converted quote value is ~$15.3K across 478 quotes**.
- **Melbourne and PWILSON** lead quote conversions.

---

### 🚀 Strategic Takeaways
- Revenue is **highly concentrated in key locations, salespeople, and customers**.
- Improving **inventory management and quote conversion strategies** could enhance operational efficiency.
- Expanding sales across **underperforming branches** may unlock additional growth.

---

## 🧠 Skills Demonstrated

- **Data Visualisation:** Designed interactive Power BI dashboards to analyse sales, customers, quotes, and backorders.
- **Data Modelling:** Built relationships between sales, customer, quote, and location datasets for integrated analysis.
- **Data Transformation (ETL):** Cleaned and prepared ERP data using Power Query for consistent reporting.
- **DAX & Metrics Development:** Created measures such as Total Sales, MTD/YTD sales, quote conversion, and backorder quantities.
- **Business Analysis:** Identified key trends in branch performance, salesperson productivity, and customer revenue.
- **Interactive Reporting:** Implemented filters, slicers, and drill-through functionality for dynamic data exploration.
- **Business Intelligence:** Transformed Microsoft Dynamics 365 Business Central data into actionable insights for decision-making.

---

## 🚀 How to Use

1. Download the `.pbix` file  
2. Open in Power BI Desktop  
3. Update OData credentials  
4. Refresh data  

> ⚠️ Live ERP connection requires Business Central access.

---

## 👤 Author

**Ajay Chavan**  
Business Analyst | Power BI Developer  
Melbourne, Australia  

🔗 LinkedIn: [https://www.linkedin.com/in/ajaychavan15/](url)
📧 Email: chavanajay1915@gmail.com  

---

## ⭐ If You Found This Useful

Feel free to fork, star ⭐, or connect for collaboration.
