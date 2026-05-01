# 🛒 Zepto SQL Data Analysis Project  

![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-blue)
![Database](https://img.shields.io/badge/PostgreSQL-Database-informational)
![Project](https://img.shields.io/badge/Project-Ecommerce%20Analytics-success)

---

## 📌 Project Overview  
The goal of this project is to simulate how data analysts in the e-commerce or retail industry work behind the scenes using SQL.

- ✅ Set up a messy, real-world e-commerce inventory database  
- ✅ Perform Exploratory Data Analysis (EDA) to explore product categories, availability, and pricing inconsistencies  
- ✅ Implement Data Cleaning to handle null values, remove invalid entries, and convert pricing from paise to rupees  
- ✅ Write business-driven SQL queries to derive insights around pricing, inventory, stock availability, revenue, and more  

---

## 🎯 Why This Project Matters  
This project demonstrates the ability to:
- Work with messy, real-world datasets  
- Perform end-to-end SQL analysis (EDA → Cleaning → Insights)  
- Translate raw data into business insights  

---

## 📁 Dataset Overview  
The dataset was sourced from Kaggle and originally scraped from Zepto’s product listings. It mimics a real-world e-commerce inventory system.

Each row represents a unique SKU (Stock Keeping Unit).

Duplicate product names exist because the same product may appear multiple times with different:
- package sizes  
- weights  
- discounts  
- categories  

---

## 🧾 Columns  

- **sku_id** – Unique identifier for each product entry  
- **name** – Product name as it appears on the app  
- **category** – Product category (Fruits, Snacks, Beverages, etc.)  
- **mrp** – Maximum Retail Price (converted from paise to ₹)  
- **discountPercent** – Discount applied on MRP  
- **discountedSellingPrice** – Final price after discount  
- **availableQuantity** – Units available in inventory  
- **weightInGms** – Product weight in grams  
- **outOfStock** – Stock availability flag (TRUE/FALSE)  
- **quantity** – Units per package  

---

## 🔧 Project Workflow  

### 1️⃣ Database & Table Creation  
```sql
CREATE TABLE zepto (
    sku_id SERIAL PRIMARY KEY,
    category VARCHAR(120),
    name VARCHAR(150) NOT NULL,
    mrp NUMERIC(8,2),
    discountPercent NUMERIC(5,2),
    availableQuantity INTEGER,
    discountedSellingPrice NUMERIC(8,2),
    weightInGms INTEGER,
    outOfStock BOOLEAN,
    quantity INTEGER
);

2️⃣ Data Import
Loaded CSV using MySQL Workbench
Counted total number of records
Viewed sample data to understand structure

3️⃣ 🔍 Exploratory Data Analysis (EDA)
Checked for null values across columns
Identified distinct product categories
Compared in-stock vs out-of-stock products
Detected duplicate product entries (multiple SKUs)

4️⃣ 🧹 Data Cleaning
Removed rows where MRP or discounted price was zero
Converted pricing from paise → rupees

5️⃣ 📊 Business Insights
Top 10 best-value products based on discount percentage
High-MRP products that are out of stock
Estimated potential revenue for each category
Expensive products (MRP > ₹500) with low discount
Top 5 categories with highest average discounts
Price-per-gram analysis for value comparison
Product grouping by weight (Low / Medium / Bulk)
Total inventory weight per category

🛠️ How to Use This Project
git clone https://github.com/VaibhavGuptaNitj/zepto-SQL-data-analysis-project
Open zepto_SQL_data_analysis.sql

Create a database
Run the SQL script
Import the dataset

Execute queries
📁 Project Structure
📦 zepto-SQL-data-analysis-project
 ┣ 📜 zepto_SQL_data_analysis.sql
 ┣ 📄 README.md
 ┗ 📊 dataset.csv

💡 Key Learnings
Real-world data cleaning using SQL
Writing business-driven queries
Handling messy e-commerce datasets
Extracting actionable insights

🔗 Repository

https://github.com/VaibhavGuptaNitj/zepto-SQL-data-analysis-project
