# **Azure-End-To-End-Data-Engineering-Project-CarSales-Data With Medallion Architecture**

This repository showcases an end-to-end Azure Data Engineering project where the Medallion Architecture is implemented for processing and transforming car sales data. It demonstrates the use of Azure services like Data Factory, Databricks, and Data Lake Gen 2 to build a scalable data pipeline.

The project involves creating a clean data pipeline from raw data ingestion to transformation and analysis-ready datasets. The repository contains the implementation, data transformation notebooks, SQL scripts, and architecture diagrams.

## **Architecture Diagram**  
Below is the architecture diagram illustrating the flow of data through the Medallion Architecture.  

![image](https://github.com/user-attachments/assets/4fe90069-f8e9-4658-abcf-1e0264518172)

---

## **Overview**  
This project showcases the implementation of a Medallion Architecture for a data engineering workflow. The architecture processes raw data, applies incremental data loading, and transforms it into a star schema for analytics using Azure tools.

### **Objective**  
To design and implement a scalable data engineering solution that follows the Medallion Architecture principles, enabling efficient data ingestion, transformation, and analysis.

### **Key Features**  
- Implements a **Medallion Architecture** with Bronze, Silver, and Gold layers for data processing.  
- Automates data ingestion from GitHub into Azure SQL Database using Azure Data Factory.  
- Enables **incremental data loading** into Azure Data Lake Gen 2.  
- Performs data transformation and cleaning using Azure Databricks notebooks and workflows.  
- Builds a **Star Schema** with **Fact** and **Dimension Tables** using Databricks workflow and implements SCD Type-1 for analytics-ready datasets.

---

## **Technologies Used**  
- **Azure Data Factory (ADF):** Orchestration of pipelines for data movement and transformation.  
- **Azure SQL Database:** Storage of raw ingested data.  
- **Azure Data Lake Gen 2:** Layered storage for Bronze, Silver, and Gold data containers.  
- **Azure Databricks:** Data transformation using notebooks and workflows.  
- **Star Schema Design:** Fact and dimension tables with SCD Type-1 implementation.  

---

## **Project Workflow**  

1. **Raw Data Ingestion:**  
   - Raw data is sourced from GitHub via HTTPS.  
   - ADF Pipeline 1 ingests data and stores it in Azure SQL Database.  

2. **Incremental Data Loading:**  
   - ADF Pipeline 2 handles incremental data loading into the Bronze container in Azure Data Lake Gen 2.  

3. **Data Transformation:**  
   - Data is cleaned and transformed using Azure Databricks notebooks.  
   - Transformed data is stored in Silver and Gold containers.  

4. **Star Schema Design and Workflow Execution:**  
   - The **Dimension Tables** and **Fact Table** are created using Azure Databricks workflow.  
   - SCD Type-1 is implemented for handling updates to dimension tables.  

---

## **Pipeline Details**  

### **Pipeline 1: Data Ingestion**  
This pipeline moves raw data from GitHub into Azure SQL Database.  
![image](https://github.com/user-attachments/assets/55ef7742-7be6-496b-8141-3596286c377d)


### **Pipeline 2: Incremental Loading**  
This pipeline manages incremental data loading into the Bronze container.  
![image](https://github.com/user-attachments/assets/4ff1d24b-b6d5-40a3-842f-358552270969)

### **Azure Databricks Workflow: Incremental Loading**  
 

---

## **Folder Structure**  
