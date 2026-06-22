# Sales End-to-End Data Engineering Project

## Project Overview

This project demonstrates the design and implementation of a modern Azure Data Engineering solution for processing and analyzing sales data. The solution leverages Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, Delta Lake, Azure Key Vault, and Microsoft Entra ID to build a scalable and secure data platform.

The architecture follows the Medallion Architecture (Bronze, Silver, Gold) pattern. Raw sales data is ingested from a SQL source system, processed through multiple transformation layers using PySpark, and finally converted into an analytics-ready Star Schema model for business reporting and decision-making.

The project also incorporates Incremental Data Loading, Delta Lake, Dimensional Modeling, and GitHub integration to simulate real-world enterprise Data Engineering practices.

---

## Solution Architecture

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/655a8e60-8282-4f65-b12d-34a4784d41b6" />


---

## Goal of the Project

The objective of this project is to build a scalable, cloud-native data engineering pipeline capable of processing large volumes of sales data while implementing modern data warehousing best practices.

### Key Objectives

* Build automated ingestion pipelines using Azure Data Factory.
* Implement Incremental Data Loading for efficient data movement.
* Design and implement Medallion Architecture.
* Perform large-scale data transformations using Azure Databricks and PySpark.
* Create analytical datasets using Star Schema modeling.
* Implement Delta Lake for reliable and optimized storage.
* Secure data assets using Azure Key Vault and Microsoft Entra ID.
* Maintain source code using GitHub version control.

---

## Technology Stack

### Cloud Services

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure Databricks
* Azure Key Vault
* Microsoft Entra ID

### Storage Formats

* Parquet
* Delta Lake

### Programming Languages

* Python
* PySpark
* SQL

### Version Control

* GitHub

---

# Part 1: Data Ingestion

The ingestion layer was implemented using Azure Data Factory to extract sales data from a SQL source system and load it into Azure Data Lake Storage Gen2.

An Incremental Loading strategy was implemented to process only newly added or modified records, reducing execution time and improving pipeline efficiency.

### Key Highlights

* SQL Database as source system.
* Azure Data Factory ingestion pipelines.
* Incremental data loading.
* Parameterized pipeline design.
* Automated orchestration.
* Metadata-driven processing.
* Raw data stored in Bronze layer as Parquet files.

### Business Value

Incremental loading minimizes processing overhead and enables efficient handling of growing datasets while reducing operational costs.

📷 Attach Screenshots:

* Source SQL Database
* Azure Data Factory Pipeline
* Incremental Load Logic
* Pipeline Execution Results

---

# Part 2: Data Transformation (Medallion Architecture)

The project follows the Medallion Architecture pattern to improve data quality, governance, and scalability.

## Bronze Layer

The Bronze Layer acts as the landing zone for raw sales data.

### Features

* Raw source data storage.
* Historical data retention.
* Parquet file format.
* Immutable data layer.

## Silver Layer

The Silver Layer performs cleansing and standardization activities.

### Transformations Performed

* Schema validation.
* Data quality checks.
* Null value handling.
* Data type standardization.
* Data enrichment.
* One Big Table (OBT) creation.

### Business Value

The Silver Layer provides a clean and consistent foundation for downstream analytics.

## Gold Layer

The Gold Layer contains curated business-ready datasets.

### Features

* Business transformations.
* Aggregations.
* Star Schema implementation.
* Delta Lake storage.

📷 Attach Screenshots:

* Bronze Layer Storage
* Silver Layer Transformations
* Databricks Notebooks
* Gold Layer Output

---

# Part 3: Star Schema Implementation

To support analytical workloads, the curated data was transformed into a dimensional model following Star Schema principles.

### Fact Tables

* Fact Sales

### Dimension Tables

* Dim Customer
* Dim Product
* Dim Date
* Dim Territory

### Key Highlights

* Dimensional Modeling.
* Star Schema Design.
* Optimized analytical queries.
* Business-friendly data model.

### Business Value

Star Schema improves query performance and simplifies reporting and analytical workloads.

📷 Attach Screenshots:

* Star Schema Diagram
* Fact Table
* Dimension Tables

---

# Part 4: Serving Layer (Delta Lake)

The Gold Layer data is stored as Delta Tables to provide reliability, consistency, and analytical performance.

### Features Implemented

* ACID Transactions.
* Delta Logs.
* Schema Enforcement.
* Schema Evolution.
* Data Versioning.
* Time Travel.

### Business Value

Delta Lake provides warehouse-grade reliability while retaining the scalability of a data lake.

📷 Attach Screenshots:

* Delta Tables
* Delta Logs
* Version History
* Time Travel Queries

---

# Security and Governance

Security controls were implemented using Azure-native services.

### Components Used

* Azure Key Vault
* Microsoft Entra ID

### Features

* Secure authentication.
* Authorization management.
* Secret management.
* Secure service connectivity.

---

# DevOps and Version Control

GitHub was used for source code management and version control.

### Benefits

* Source control.
* Change tracking.
* Collaboration.
* Version management.

📷 Attach Screenshots:

* GitHub Repository
* Project Structure

---

# Skills Demonstrated

### Azure Services

* Azure Data Factory
* Azure Data Lake Storage Gen2
* Azure Databricks
* Azure Key Vault
* Microsoft Entra ID

### Data Engineering Concepts

* Incremental Loading
* Medallion Architecture
* One Big Table (OBT)
* Star Schema
* Dimensional Modeling
* Delta Lake
* Data Warehousing
* ETL/ELT Pipelines

### Programming

* Python
* PySpark
* SQL

---

# Conclusion

This project demonstrates an end-to-end Azure Data Engineering solution that combines scalable data ingestion, distributed processing, dimensional modeling, and Delta Lake capabilities to build a modern analytics platform for sales data. The implementation follows industry-standard data engineering practices and provides a strong foundation for business intelligence and advanced analytics.
