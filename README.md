# **Azure-End-To-End-Data-Engineering-Project-CarSales-Data With Medallion Architecture**


## **Overview**  
This project showcases the implementation of a Medallion Architecture for a data engineering workflow. The architecture processes raw data, applies incremental data loading, and transforms it into a star schema for analytics using Azure tools.

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

4. **Star Schema Design:**  
   - One table is broken into:  
     - **Fact Table:** Contains transactional data.  
     - **Dimension Tables:** Contain descriptive attributes.  
   - SCD Type-1 is implemented for handling updates to dimension tables.  

---

## **Architecture Diagram**  
Below is the architecture diagram illustrating the flow of data through the Medallion Architecture.  

![Architecture Diagram](path/to/architecture-diagram.png)  

---

## **Pipeline Details**  

### **Pipeline 1: Data Ingestion**  
This pipeline moves raw data from GitHub into Azure SQL Database.  
![Pipeline 1 Diagram](path/to/pipeline-1-diagram.png)  

### **Pipeline 2: Incremental Loading**  
This pipeline manages incremental data loading into the Bronze container.  
![Pipeline 2 Diagram](path/to/pipeline-2-diagram.png)  

---

## **Folder Structure**  
