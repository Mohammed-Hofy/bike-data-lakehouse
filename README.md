# Bike Data Lakehouse

This project demonstrates the design and implementation of a modern Data Lakehouse using the Medallion Architecture (Bronze, Silver, Gold) on Databricks.

The pipeline ingests raw data from multiple source systems, performs data cleansing and transformation using PySpark and SQL, and builds business-ready dimensional models optimized for analytics and reporting.

---

# Technologies

- Databricks
- PySpark
- Spark SQL

---

# Architecture

The project follows the Medallion Architecture.

## Bronze Layer

The Bronze layer stores raw data exactly as received from the source systems.

No transformations are applied at this stage, making it the foundation for all downstream processing.

### Sources

- CRM System
- ERP System

---

## Silver Layer

The Silver layer cleanses, validates, and standardizes the raw data.

Main transformations include:

- Data type conversions
- Data quality validation
- Missing value handling
- Duplicate removal
- Standardization of categorical values
- Date validation and correction
- Data enrichment

The cleaned datasets are stored as Delta tables for further processing.

---

## Gold Layer

The Gold layer integrates the cleaned Silver tables into analytical models following a Star Schema design.

This layer is optimized for reporting, dashboards, and business intelligence.

### Dimension Tables

- dim_customers
- dim_products

### Fact Table

- fact_sales

---

# Data Model

The Gold layer implements a Star Schema.

### Fact Table

- fact_sales

### Dimension Tables

- dim_customers
- dim_products

---

# ETL Pipeline

The pipeline executes in the following order:

1. Load raw source files into the Bronze Layer.
2. Clean and standardize the data in the Silver Layer using PySpark.
3. Integrate datasets and build analytical models in the Gold Layer.
4. Produce business-ready tables for reporting and analytics.
