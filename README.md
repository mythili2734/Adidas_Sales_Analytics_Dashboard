# 👟 Adidas Sales Analytics Dashboard | Microsoft Fabric & Power BI

## 📌 Project Overview

This project demonstrates an end-to-end Data Engineering and Business Intelligence solution using Microsoft Fabric and Power BI. The solution follows the Medallion Architecture (Bronze, Silver, Gold) to transform raw sales data into meaningful business insights.

The dashboard provides comprehensive analysis of Adidas sales performance across products, retailers, regions, states, and sales channels to support data-driven decision-making.

---

## 🎯 Business Objective

The objective of this project is to:

- Analyze overall sales performance.
- Identify top-selling products.
- Evaluate retailer performance.
- Compare regional sales and profitability.
- Analyze sales methods.
- Track monthly sales trends.
- Identify top-performing states.
- Build an interactive dashboard for business users.

---

## 🛠️ Technologies Used

- Microsoft Fabric
- Lakehouse
- PySpark
- Delta Tables
- Medallion Architecture
- Semantic Model
- Power BI Desktop
- DAX
- Microsoft Excel

---

## 📂 Dataset

**Dataset Name**

Adidas US Sales Datasets.xlsx

Dataset contains:

- Retailer
- Retailer ID
- Invoice Date
- Region
- State
- City
- Product
- Price per Unit
- Units Sold
- Total Sales
- Operating Profit
- Operating Margin
- Sales Method

---

## 🏗️ Project Architecture

```
Excel Dataset
      │
      ▼
Microsoft Fabric Lakehouse
      │
      ▼
Bronze Layer
      │
      ▼
Silver Layer
      │
      ▼
Gold Layer
      │
      ▼
Semantic Model
      │
      ▼
Power BI Dashboard
```

---

# 🥉 Bronze Layer

## Purpose

Store the raw data exactly as received from the source.

### Activities

- Loaded Excel dataset into Lakehouse
- Preserved raw data
- Removed unwanted "Unnamed" column
- Stored data as Delta Table

### Output

```
bronze_adidas_sales
```

---

# 🥈 Silver Layer

## Purpose

Clean and transform the raw data.

### Activities

- Renamed columns
- Converted data types
- Removed duplicate records
- Handled null values
- Created Year column
- Created Month column
- Created Month Name column
- Created Quarter column

### Output

```
silver_adidas_sales
```

---

# 🥇 Gold Layer

## Purpose

Create business-ready tables for reporting.

### Fact Table

### fact_sales

Attributes

- sales_id
- date_key
- product_key
- retailer_key
- region_key
- sales_method_key
- units_sold
- price_per_unit
- total_sales
- operating_profit
- operating_margin

---

### Dimension Tables

#### dim_product

- product_key
- product

#### dim_retailer

- retailer_key
- retailer_id
- retailer

#### dim_region

- region_key
- region
- state
- city

#### dim_date

- date_key
- invoice_date
- day
- month
- month_name
- quarter
- year

#### dim_sales_method

- sales_method_key
- sales_method

---

## ⭐ Star Schema

```
               Dim_Product
                    |
                    |
Dim_Retailer ---- Fact_Sales ---- Dim_Date
                    |
                    |
               Dim_Region
                    |
                    |
          Dim_Sales_Method
```

---

# 🧠 Semantic Model

Created relationships between all Fact and Dimension tables.

### Relationships

- Dim_Product → Fact_Sales
- Dim_Retailer → Fact_Sales
- Dim_Date → Fact_Sales
- Dim_Region → Fact_Sales
- Dim_Sales_Method → Fact_Sales

---

# 📊 Power BI Dashboard

## KPI Cards

- Total Sales
- Units Sold
- Operating Profit
- Orders Count
- Operating Margin %
- Average Price per Unit

---

## Dashboard Visualizations

- Units Sold by Product
- Operating Margin % by Product
- Total Sales by Retailer
- Total Sales by Region
- Total Sales by Sales Method
- Sales Trend by Year & Month
- Operating Profit by Region
- Top 10 States by Total Sales

---

## Dashboard Filters

- Year
- Region
- State
- Product
- Retailer
- Sales Method

---

# 📈 Key Business Insights

- Total Sales exceeded **$899.90 Million**
- Over **2 Million Units Sold**
- West Region generated the highest sales
- West Region achieved the highest operating profit
- West Gear is the top-performing retailer
- Men's Street Footwear is the best-selling product
- In-store sales contribute the highest revenue
- New York and California are the highest revenue-generating states
- Sales showed significant growth throughout 2021

---

# ⚠️ Challenges Faced

- Extra "Unnamed" column while reading Excel
- Incorrect data types
- Duplicate records
- Null values
- Creating Star Schema
- Building Semantic Model
- Creating DAX measures

---

# ✅ Solutions

- Removed unnecessary columns
- Converted data types using PySpark
- Removed duplicates
- Handled null values
- Created Fact and Dimension tables
- Built a Semantic Model
- Created reusable DAX measures

---

# 🚀 Future Enhancements

- Automate data ingestion using Fabric Pipelines
- Connect to SQL Server or Azure SQL Database
- Implement Incremental Refresh
- Add Row-Level Security (RLS)
- Publish to Power BI Service

---

# 📷 Dashboard Preview

<img width="960" height="540" alt="Screenshot 2026-07-01 112411" src="https://github.com/user-attachments/assets/d63b533f-50e9-46b9-997e-cb563beac330" />


# 📁 Project Structure

```
Adidas-Sales-Analytics/
│
├── Dataset/
│   └── Adidas_US_Sales_Datasets.xlsx
│
├── Notebooks/
│   ├── Bronze.ipynb
│   ├── Silver.ipynb
│   └── Gold.ipynb
│
├── PowerBI/
│   └── Adidas_Sales_Analytics.pbix
│
├── Dashboard/
│   └── Dashboard.png
│
└── README.md
```

---

# 💡 Skills Demonstrated

- Microsoft Fabric
- Lakehouse
- Medallion Architecture
- PySpark
- Data Cleaning
- Data Transformation
- Delta Tables
- Star Schema
- Semantic Modeling
- DAX
- Power BI
- Data Visualization

---

# 👩‍💻 Author

**Mythili Maram**

Aspiring Data Engineer | Power BI Developer

---

## ⭐ If you found this project helpful, please give it a Star!
