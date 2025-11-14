# Azure Databricks End-to-End Data Engineering Project (2025)

This repository contains a **production-grade, end-to-end Azure Databricks project**, built by following the **step-by-step guide from Ansh Lamba**. The project demonstrates modern data engineering concepts, pipeline automation, and best practices suitable for interviews and real-world enterprise applications.  

---

## Project Overview

- **Objective:** Build a fully automated data engineering pipeline in Azure Databricks covering ingestion, transformation, governance, and storage.  
- **Architecture:** **Medallion architecture** (Bronze → Silver → Gold) with streaming and batch processing.  
- **Domain:** Retail datasets (orders, customers, products, regions).  
- **Focus Areas:**  
  - Incremental streaming ingestion with **exactly-once semantics**.  
  - **PySpark transformations** and **Python OOP** for reusable logic.  
  - **Unity Catalog** for data governance.  
  - **Slowly Changing Dimensions (SCD) Type 1 and Type 2** handling.  
  - **Delta Live Tables (DLT)** for declarative ETL pipelines.  
  - Pipeline orchestration fully within Databricks.  

---

## Tools and Technologies Used

| Category | Tools / Frameworks |
|----------|------------------|
| Cloud & Storage | Azure Portal, Azure Storage Account (Data Lake Gen2), Resource Groups |
| Data Platform | Azure Databricks (Workspace, Clusters, Jobs) |
| Data Processing | PySpark, Spark Structured Streaming, Auto Loader, Delta Lake, Delta Format |
| ETL Automation | Delta Live Tables (DLT), Databricks Jobs workflows |
| Data Governance | Unity Catalog, External Locations, Role-Based Access Control |
| Data Modeling | Medallion Architecture, Star Schema, Slowly Changing Dimensions (SCD) Type 1 & 2 |
| Data Formats | Parquet (columnar, schema-support) |
| Orchestration | Parameterized notebooks, job dependencies, parallel & sequential execution |

---

## Key Concepts

- **Medallion Architecture:** Layers data into Bronze (raw), Silver (cleaned/enriched), Gold (curated).  
- **Spark Structured Streaming & Auto Loader:** Incremental and streaming ingestion with exactly-once guarantees.  
- **Idempotency:** Ensures each record is processed exactly once.  
- **Unity Catalog:** Centralized governance and access control for Databricks.  
- **Delta Live Tables (DLT):** Declarative framework for automated pipelines, data quality, and SCD management.  
- **SCD Type 1:** Overwrites existing dimension records (no history).  
- **SCD Type 2:** Maintains historical records with start/end dates.  
- **UPSERT / Merge:** Efficient incremental update/insert in Delta tables.  
- **Surrogate Keys:** Artificial unique keys for dimension tables enabling efficient joins.  
- **Python OOP in PySpark:** Reusable classes for transformations, window functions, and analytics logic.  

---

## Project Workflow

1. **Azure Setup:**  
   - Create a free Azure account and resource group.  
   - Configure **Azure Storage Account (Data Lake Gen2)** with hierarchical namespace.  
   - Create containers for `source`, `bronze`, `silver`, and `gold` layers.  
   - Upload initial Parquet datasets to the `source` folder.  

2. **Databricks Setup:**  
   - Create a **Databricks workspace** and clusters (all-purpose and job clusters).  
   - Configure **Azure Databricks Access Connector** to securely read/write from Data Lake.  
   - Assign necessary roles (e.g., Storage Blob Contributor).  

3. **Unity Catalog & Governance:**  
   - Create catalogs and schemas for Bronze, Silver, Gold layers.  
   - Map **external locations** to Data Lake containers.  
   - Configure role-based permissions for access control.  

4. **Data Ingestion:**  
   - Use **no-code ingestion** for static files.  
   - Bronze layer streaming ingestion using **Auto Loader** with checkpointing and schema evolution.  

5. **Silver Layer Transformations:**  
   - Data cleaning and enrichment using **PySpark transformations**.  
   - Implement **Python OOP** for reusable transformation logic.  
   - Save data in **Delta format**.  

6. **Gold Layer Modeling:**  
   - Dimension and fact tables following **star schema**.  
   - Implement **SCD Type 1 & 2** logic.  
   - Use **Delta Live Tables** for automated SCD Type 2 pipelines.  

7. **Fact Table Construction & Orchestration:**  
   - Join silver data with gold dimensions, apply surrogate keys.  
   - UPSERT logic for incremental updates using Delta Lake.  
   - Orchestrate end-to-end workflow using **Databricks Jobs** with dependencies and parallel execution.  

---

## Acknowledgements

This project was **developed following the original step-by-step guide by Ansh Lamba**, available [here](https://youtu.be/4uKRzDf0zIc?si=zj4BGnBxjRNXje7U). All methodologies, pipeline designs, and theory references are based on the techniques demonstrated in the video.  

---
