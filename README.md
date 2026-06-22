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

Source SQL Database
<img width="1894" height="649" alt="1000193913" src="https://github.com/user-attachments/assets/c9204778-50b6-4e84-8b7b-8acf5b8b0a11" />

<img width="1668" height="953" alt="image" src="https://github.com/user-attachments/assets/f34e955c-3960-4393-a029-3c5747053a44" />

Azure Data Factory Pipeline
<img width="1905" height="591" alt="1000193915" src="https://github.com/user-attachments/assets/4fd13f5e-30cd-4a53-9fef-e056c8eaa0b8" />

Pipeline Execution Results
<img width="1150" height="519" alt="1000193920" src="https://github.com/user-attachments/assets/4a331c66-a780-47b2-932d-019c7353625a" />


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


* Silver Layer Transformations
<img width="1317" height="224" alt="1000193921" src="https://github.com/user-attachments/assets/53e24491-e87f-41f2-8cbe-433ef01d9419" />
<img width="1751" height="591" alt="1000193922" src="https://github.com/user-attachments/assets/ae3ba6ef-9047-483b-a2fa-7b923a84abbf" />

* Gold Layer Output
<img width="1442" height="320" alt="1000193926" src="https://github.com/user-attachments/assets/fe0a3e0a-203a-4e58-ab07-c6026d81ca6f" />
<img width="1146" height="485" alt="1000193928" src="https://github.com/user-attachments/assets/c39ad61a-da2a-4a66-98e8-6453ac2eca95" />
<img width="1414" height="355" alt="1000193929" src="https://github.com/user-attachments/assets/4b082616-a7f7-427a-994f-526e1e84da04" />




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
<img width="1228" height="782" alt="1000193927" src="https://github.com/user-attachments/assets/fa42c099-f4d0-4a44-aabb-7ddcdb4cd0b0" />

<img width="1444" height="532" alt="1000193930 (1)" src="https://github.com/user-attachments/assets/c7c03897-5a0c-4803-a0b8-e2a3beae9f7d" />

* Fact Table
<img width="1348" height="895" alt="1000193931" src="https://github.com/user-attachments/assets/106c47b9-3683-48ae-b44a-6aabf9186435" />

<img width="1564" height="855" alt="1000193932 (1)" src="https://github.com/user-attachments/assets/9aae3f2e-5f5b-422e-bb56-1f8029a8e16e" />


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
