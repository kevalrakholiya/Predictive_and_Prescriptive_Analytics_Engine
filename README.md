# Predictive and Prescriptive Analytics Engine for E-Commerce

## Overview

This project presents an end-to-end data engineering and analytics solution built on a Brazilian e-commerce dataset. It demonstrates how raw transactional data can be transformed into a structured data warehouse and leveraged for advanced analytics and business intelligence.

The system integrates ETL pipelines, a PostgreSQL-based warehouse, and Power BI dashboards to support descriptive, predictive, and prescriptive analytics use cases. The primary goal is to enable data-driven decision-making by providing clean, reliable, and query-optimized data.

---

## Data Source

The dataset used in this project is publicly available:

- Brazilian E-Commerce Public Dataset by Olist  
  https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

### Steps to Download Data

1. Visit the dataset link above
2. Download the dataset (ZIP format)
3. Extract files into the `/data` directory of this repository

---

## Project Structure
# Project Directory Structure

```text
Predictive_and_Prescriptive_Analytics_Engine/
│
├── Analytics/
│   ├── descriptive_exploration/
│   │   ├── correlation_analysis.sql
│   │   ├── monthly_analysis.sql
│   │   ├── geographic_analysis.sql
│   │   └── statistical_summary.sql
│   │
│   ├── predictive_exports/
│   │   ├── cross_validation_results.csv
│   │   ├── confusion_matrix.csv
│   │   ├── feature_importance.csv
│   │   ├── customer_satisfaction_predictions.csv
│   │   └── decision_tree_outputs.csv
│   │
│   ├── prescriptive_exports/
│   │   ├── delivery_cost_analysis.csv
│   │   ├── delivery_optimization_results.csv
│   │   └── warehouse_optimization.csv
│   │
│   ├── descriptive_analysis.sql
│   ├── predictive_analysis.sql
│   └── prescriptive_analysis.sql
│
├── Dashboards/
│   └── BI_Dashboard.pbix
│
├── Database/
│   ├── schema_creation.sql
│   └── analytical_queries.sql
│
├── Documentation/
│   ├── ERD.pdf
│   ├── data_dictionary.xlsx
│   └── user_guide.pdf
│
├── ETL/
│   ├── extract_transform_load.ktr
│   ├── tr_load_dim_geography.ktr
│   ├── tr_load_dim_customer.ktr
│   ├── tr_load_dim_orders.ktr
│   ├── tr_load_dim_payment.ktr
│   ├── tr_load_dim_products.ktr
│   ├── tr_load_dim_sellers.ktr
│   ├── tr_load_fact_sales.ktr
│   └── tr_load_fact_delivery.ktr
│
├── Screenshots/
│   └── BI_Dashboard.pdf
│
├── .gitignore
├── CONTRIBUTING.md
└── README.md

## Architecture
```mermaid
graph TD
    A[Raw Data Sources] --> B[ETL Pipelines: Pentaho Data Integration]
    B --> C[Data Cleaning and Transformation]
    C --> D[PostgreSQL Data Warehouse: Star Schema]
    D --> E[Analytics Layer: SQL + Python]
    E --> F[Power BI Dashboard]

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style D fill:#bbf,stroke:#333,stroke-width:2px
    style F fill:#bfb,stroke:#333,stroke-width:2px


---

## Data Warehouse Design

The warehouse is modeled using a star schema to optimize analytical queries.

### Fact Table
- `fact_orders`  
  Contains transactional metrics such as order value, timestamps, and delivery performance.

### Dimension Tables
- `dim_customers`
- `dim_products`
- `dim_sellers`
- `dim_time`
- `dim_geolocation`

This design enables efficient aggregation and slicing across business dimensions.

---

## ETL Pipeline

ETL pipelines are implemented using Pentaho Data Integration.

### Key Responsibilities

- Extract data from CSV files
- Clean and standardize inconsistent records
- Handle missing values and duplicates
- Transform data into dimension and fact tables
- Load processed data into PostgreSQL

---

## Getting Started

### 1. Clone Repository

```bash
git clone https://github.com/kevalrakholiya/Predictive_and_Prescriptive_Analytics_Engine.git
cd Predictive_and_Prescriptive_Analytics_Engine
```

## 2. Set Up Database

- Install PostgreSQL  
- Create a new database  

```sql
CREATE DATABASE ecommerce_dw;
```
- Update database credentials inside ETL configuration files

## 3. Run ETL Pipelines
- Open Pentaho Data Integration (Spoon)
- Load .ktr or .kjb files from /etl directory
- Execute pipelines to populate the warehouse
  
## 4. Launch Dashboard
- Open Power BI Desktop
- Load .pbix file from /dashboards
- Connect to PostgreSQL database
- Refresh data


