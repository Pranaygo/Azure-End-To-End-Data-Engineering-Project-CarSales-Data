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

### **Azure Databricks Workflow: dimensions and fact tables**  

 ![image](https://github.com/user-attachments/assets/fa3c1295-5e00-42ce-aedc-d3b47a558f02)

### **Azure SQL Database: Tables and StoredProcedures**  

![image](https://github.com/user-attachments/assets/abea55b8-9a30-48f4-b633-c200d312fcbc)

### **Azure Resource Group:**  

![image](https://github.com/user-attachments/assets/d7068f49-eec5-45cc-a891-24b8e9d2da85)


---

## **How to Run This Project**

To run this project, follow the steps outlined below. Ensure you meet the prerequisites and have the necessary permissions and configurations set up in your Azure environment.

### **Prerequisites**

- **Azure Subscription:** You need an active Azure subscription to use Azure services such as Azure Data Factory, Azure Databricks, and Azure Data Lake Gen 2.
- **Azure Data Factory (ADF):** Basic understanding of ADF to manage and execute pipelines.
- **Azure Databricks Workspace:** A Databricks workspace to run notebooks and workflows.
- **GitHub Account:** For data ingestion from GitHub (if using the raw data source).
- **Azure CLI:** Installed and configured for managing Azure resources (optional for advanced users).
- **Azure SQL Database:** For storing and processing raw data.
- **Python (Optional):** For additional transformations and scripts in Databricks if needed.

### **Steps to Run the Project**

1. **Set Up Azure Data Factory (ADF):**
   - **Create Pipelines:**  
     Set up two pipelines in Azure Data Factory:
     - **Pipeline 1**: For ingesting data from GitHub into Azure SQL Database.
     - **Pipeline 2**: For incremental data loading into Azure Data Lake Gen 2 (Bronze layer).
   - **Configure Linked Services:**  
     Set up Linked Services for the following:
     - GitHub (for raw data ingestion).
     - Azure SQL Database.
     - Azure Data Lake Gen 2.

2. **Set Up Azure Databricks:**
   - **Create a Databricks Workspace:**  
     Set up an Azure Databricks workspace and configure the clusters.
   - **Import Notebooks:**  
     Import the Databricks notebooks for data transformation, which include:
     - Bronze to Silver transformation.
     - Silver to Gold transformation.
   - **Run Notebooks:**  
     Execute the notebooks in the workspace for data processing, transformation, and loading into the Gold layer.

3. **Verify Data Storage:**
   - **Azure SQL Database:**  
     Check if the raw data from GitHub has been loaded into the Azure SQL Database.
   - **Azure Data Lake Gen 2:**  
     Verify that the data has been correctly loaded into the Bronze container, processed in the Silver container, and transformed into the Gold container.

4. **Star Schema Design:**
   - **Run the Databricks Workflow:**  
     Execute the workflow in Databricks to create the Star Schema and implement SCD Type-1 for dimension updates.
   - **Verify Fact and Dimension Tables:**  
     Ensure that the Fact table and Dimension tables are created as expected.

5. **Optional - Customize and Extend:**
   - Modify the notebooks or pipelines to suit your specific use case or extend the functionality.
   - Implement further data quality checks, automation, or scheduling based on your needs.

### **Post-Execution**

After running the pipelines and transformations, you should see the final processed data in the Gold layer, ready for analytics and reporting.

