# Corporate Sales Performance Dashboard

[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)
[![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](#)
[![Data Engineering](https://img.shields.io/badge/Data_Engineering-2596be?style=for-the-badge)](#)

> **[View the Interactive Dashboard Live on my Portfolio](https://intelidatos.cl/en/portfolio/)**

## Project Overview
A robust, enterprise-grade Business Intelligence solution designed for Sales Management. This dashboard provides deep insights into geographic performance, product profitability, and sales team productivity, utilizing historical data to calculate YoY (Year-over-Year) metrics and KPIs.

## Technical Architecture
This project goes beyond a simple .pbix file. It is built adopting software engineering best practices for Business Intelligence:

* **Version Control Ready:** Saved in the modern Power BI Project (.pbip) format using the Tabular Model Definition Language (TMDL). This allows for granular version tracking and CI/CD pipeline readiness.

* **Data Modeling:** Strict Star Schema implementation ensuring optimal query performance and referential integrity.

* **Dynamic Time Intelligence:** Features a dynamically generated Dim_Calendar built entirely in DAX, forcing a US-English locale (en-US) for international standardization.

* **Security & Environment Variables:** Data source paths are abstracted using Power Query Parameters (CSV_DIR), protecting local environments and making deployment to production seamless.

## Data Schema Definition

The semantic model expects the following flat-file structure as its data source:

* **dim_product.csv:** `product_id` (Int), `product_name` (Text), `product_cat` (Text), `short_name` (Text)
* **dim_seller.csv:** `seller_id` (Int), `seller_name` (Text)
* **dim_city.csv:** `city_id` (Int), `region_id` (Int), `city_name` (Text)
* **dim_region.csv:** `region_id` (Int), `region_sort` (Int), `region_name` (Text), `short_name` (Text)
* **fact_sales.csv:** `city_id` (Int), `client_id` (Int), `fecha_id` (Date), `product_id` (Int), `sale_amount` (Decimal), `sale_quantity` (Int), `sell_id` (Int), `seller_id` (Int)



## How to Run Locally

If you want to clone this repository and run it on your local machine:
1. Clone the repository: `git clone https://github.com/cesarmarambio/en-powerbi-corporate-sales.git`
2. Open the `pfes01_en_sales.pbip` file in Power BI Desktop.
3. Open **Power Query Editor** (Transform Data).
4. Update the `CSV_DIR` parameter to point to the local folder containing the source files formatted as per the Data Schema.
5. Apply changes and refresh the semantic model.

---
*Developed by **César Marambio** | Data Engineer & BI Specialist*