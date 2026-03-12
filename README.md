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

## 🏢 Business Context

Designed for a distribution-based ERP environment where:

- Multiple products and brands are managed
- Inventory turnover impacts cash flow
- Backorders affect customer satisfaction
- Reporting is required across transactional ERP tables

The key challenge was transforming ERP transactional data into an optimised analytical model.

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

### Tables Integrated

- Sales Header  
- Sales Line  
- Purchase Header  
- Purchase Line  
- Item  
- Vendor  
- Customer  
- Item Ledger Entries  

### Key Technical Challenges Resolved

- HTTP 400 errors due to missing Document IDs  
- Relationship modelling between Header and Line tables  
- Handling archived documents  
- Optimising refresh performance  
- Creating efficient data model relationships  

---

## 📊 Dashboard Modules

## 📊 Dashboard Modules

### 1️⃣ Total Sales Analysis
- 📅 **Total Sales by Month**
- 📍 **Sales by Location Code**
- 👤 **Sales by Salesperson**
- 📈 **Monthly Sales Trends & Performance**

---

### 2️⃣ Top Customers Performance
- 📦 **Top 20 Customers by Revenue**
- 🏢 **Customer Sales by Branch**
- 👤 **Customer Sales by Salesperson**
- 📊 **Revenue Contribution % by Customer**

---

### 3️⃣ Backorders Monitoring
- 🔁 **Backorders by Salesperson**
- 👤 **Backorders by Customer**
- 📦 **Backorders by Product / Item**
- 💰 **Outstanding Order Value**

---

### 4️⃣ Open Quotes Analysis
- 📝 **Open Quote Value by Location**
- 👤 **Open Quotes by Salesperson**
- 💰 **Total Outstanding Quote Value**
- 📊 **Quote Pipeline Overview**

---

### 5️⃣ Quote Conversion Performance
- 📈 **Converted Quote Value by Location**
- 👤 **Converted Quotes by Salesperson**
- 🔄 **Quote-to-Sales Conversion Rate**
- 💰 **Revenue from Converted Quotes**

---

### 6️⃣ Location & Salesperson Performance
- 🏆 **Total Sales by Location Code**
- 👤 **Sales by Salesperson**
- 📊 **Branch-wise Revenue Distribution**
- 📈 **Salesperson Performance Ranking**
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




---

## 📌 Business Insights Generated

- Top 10 customers contribute ~60% of total revenue  
- Vendor concentration risk identified across major brands  
- Backorders concentrated in high-demand SKUs  
- Purchase order exposure identified across suppliers  

---

## 🚀 How to Use

1. Download the `.pbix` file  
2. Open in Power BI Desktop  
3. Update OData credentials  
4. Refresh data  

> ⚠️ Live ERP connection requires Business Central access.

---

## 💼 Skills Demonstrated

✔ ERP Data Extraction via API  
✔ Enterprise Data Modelling  
✔ Advanced DAX Calculations  
✔ KPI Framework Development  
✔ Business Insight Communication  
✔ Performance Optimisation  

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
