Sales Data CDC Pipeline
📌 Overview
This project implements a Delta Live Tables (DLT) pipeline in Databricks for processing Customers and Sales data using Change Data Capture (CDC) logic.
The pipeline loads, transforms, and maintains data in Bronze, Silver, and Gold layers for analytics and reporting.

🏗 Pipeline Structure
The pipeline follows a medallion architecture:

1. Bronze Layer
Ingests raw data from the source system (CSV/Parquet/Delta).

Stores unmodified data for traceability.

Supports CDC ingestion with apply_changes.

2. Silver Layer
Cleans, filters, and deduplicates data.

Applies CDC merge logic using APPLY CHANGES INTO.

Prepares standardized customers_silver and sales_silver tables.

3. Gold Layer
Aggregates and enriches data for analytics.

Produces KPI-focused tables (e.g., sales by region, customer activity).

Ready for BI dashboards (e.g., Power BI, Tableau, Databricks SQL).

⚙ Technologies Used
Databricks Delta Live Tables (DLT)

Databricks SQL

Change Data Capture (CDC)

Medallion Architecture

Delta Lake

🚀 How to Run
Import the Pipeline

In Databricks, go to Workflows → Delta Live Tables → Create Pipeline.

Import the .dbc file provided in this repo.

Configure Pipeline Settings

Name: salesdata_cdc_pipeline

Source: Set your source dataset location in the configuration.

Target Schema: Set your database/schema for storing results.

Start the Pipeline

Click Start to begin ingestion and transformation.

DLT will manage dependencies and data freshness automatically.

🗂 Output Tables
Bronze:

customers_bronze

sales_bronze

Silver:

customers_silver

sales_silver

Gold:

sales_summary_gold

customer_sales_gold

📈 Example Use Cases
Track customer activity over time.

Analyze sales trends with CDC-updated data.

Feed aggregated sales insights to BI dashboards.

📝 Notes
CDC logic ensures only changed data is processed, improving efficiency.

Gold layer tables are optimized for fast querying.
