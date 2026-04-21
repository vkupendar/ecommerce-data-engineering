# E-Commerce Data Engineering Project

## Overview
This project demonstrates an end-to-end **Data Engineering pipeline** built using **PySpark and Databricks**.  
The goal is to transform raw CSV data into a structured **Star Schema** for efficient analytics.

---

## Tech Stack
- Python  
- PySpark  
- SQL  
- Databricks  
- Delta Lake  

---

## Dataset
- Brazilian E-Commerce Public Dataset (from Kaggle)

---

## Architecture

Raw CSV Files → PySpark → Data Cleaning → Transformations → Star Schema → Delta Tables → SQL Analytic

---

## Data Modeling

### Fact Table
- `fact_orders`
  - order_id  
  - customer_id  
  - product_id  
  - seller_id  
  - price  
  - freight_value  
  - total_payment  
  - order_status  
  - order_purchase_timestamp  

---

## Dimension Tables

- `dim_customers`
  - customer_id  
  - customer_unique_id  
  - customer_city  
  - customer_state  

- `dim_products`
  - product_id  
  - product_category_name  

- `dim_sellers`
  - seller_id  
  - seller_city  
  - seller_state  

- `dim_date`
  - date  
  - year  
  - month  
  - day  

---

## Pipeline Steps

1. Data ingestion from CSV files  
2. Data validation & basic cleaning  
3. Joining transactional tables  
4. Creating fact and dimension tables  
5. Storing data as Delta tables in Databricks  
6. Running analytical SQL queries  

---

## Sample Queries

### Total Sales
```sql
SELECT SUM(price) AS total_sales
FROM fact_orders;
