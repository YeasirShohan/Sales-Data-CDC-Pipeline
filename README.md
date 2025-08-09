# 🛠 Databricks Delta Live Tables (DLT) Pipeline

## 📌 Project Overview
This project implements a **Databricks Delta Live Tables (DLT)** pipeline to ingest, transform, and serve data for analytics.  
It follows a **Medallion Architecture** approach with **Bronze → Silver → Gold** layers, ensuring data quality, lineage, and scalability.

---

## 🏗 Pipeline Structure
┌────────────┐
│ Bronze │ → Raw data ingestion from source
└─────┬──────┘
↓
┌────────────┐
│ Silver │ → Data cleaning, joining, and enrichment
└─────┬──────┘
↓
┌────────────┐
│ Gold │ → Curated datasets for analytics & BI
└────────────┘

---

## 🗂 Pipeline Tasks
### 1. **Bronze Layer**
- Ingest raw **Customers** and **Sales** data from the source.
- Store as Delta tables for further processing.

### 2. **Silver Layer**
- Apply cleaning and standardization.
- Enrich data with derived fields.
- Implement **CDC (Change Data Capture)** logic to handle incremental updates.

### 3. **Gold Layer**
- Create final curated datasets ready for reporting and dashboards.
- Join multiple datasets (if applicable) or prepare them for BI tools.

---

## ⚙️ Technology Stack
- **Databricks** (Delta Live Tables)
- **PySpark**
- **Delta Lake**
- **Medallion Architecture**

---

## 📁 Project Structure
DLT_Pipeline/
├── bronze_layer.py # Ingest raw data
├── silver_layer.py # Clean & transform
├── gold_layer.py # Create curated datasets


---

## 🚀 Getting Started
### 1. Import Pipeline
- Import the `.dbc` file into your Databricks workspace.

### 2. Configure Cluster
- Use a **DLT-compatible cluster**.
- Enable **Photon** for performance optimization.

### 3. Run the Pipeline
- Go to **Workflows → Delta Live Tables**.
- Create a new pipeline and select the imported notebooks.
- Configure source paths and target database names.
- Click **Start** to run the pipeline.

---

## 🔄 Change Data Capture (CDC)
- CDC is implemented using the `MERGE INTO` syntax in Delta Lake.
- Ensures that only new or updated records are processed.

---

## 📊 Example Output
- **Bronze:** `bronze_customers`, `bronze_sales`
- **Silver:** `silver_customers_clean`, `silver_sales_enriched`
- **Gold:** `gold_customer_sales_summary`

---

## 📜 License
This project is licensed under the MIT License.
