# End-to-end-Data-Engineer-Project-E-commerce
## Project Description:
This project focuses on building an efficient data pipeline tailored for e-commerce, handling diverse datasets from various sources. We start by extracting data from CSV files, followed by light transformations using Alteryx. The cleaned data is then loaded into SQL Server for staging, where it undergoes further transformations with Power Query to prepare it for deeper analysis. The refined data is modeled in SQL Server to establish relationships and structure, setting the stage for powerful reporting.

The final step involves leveraging Power BI for insightful data visualization, creating interactive dashboards that provide key business metrics and trends. This end-to-end solution not only streamlines the data processing workflow but also delivers meaningful insights, helping businesses make informed, data-driven decisions.
## Project Architecture:

<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Project%20Flow.png">

* Data is ingested and orchestrated using Azure Data Factory.
* Raw data is stored in the <b>Silver layer</b> of Azure Data Lake Storage Gen2.
* Data is processed and cleansed using Azure Databricks, with results stored in the Silver layer.
* Further transformations and analytics are performed, producing business-ready data in the Gold layer.
* Azure Synapse Analytics is used for large-scale data warehousing and analytics.
* Final insights are visualized using Power BI.
   
## Current Environment
* Utilized the E-commerce dataset from Microsoft.
* Set up an on-premises Microsoft SQL server on a personal computer.
* Imported the dataset using Microsoft SQL Server Management Studio.
* Created a new user profile, "ndp."
* Saved "ndp" profile's password credentials as a Secret in Azure Key Vault.

<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/on-premises%20Microsoft%20SQL%20server.png">

## Azure Technologies Used:

This project leverages the following Azure services:

1. **Azure Data Factory (ADF)**
   - Used for orchestrating and automating data movement and data transformation workflows.
2. **Azure Data Lake Storage Gen2**
   - Serves as the primary storage solution, organizing data into Silver (cleansed), and Gold (transformed) layers.
3. **Azure Databricks**
   - Employed for data processing, transformation, and advanced analytics tasks.
4. **Azure Synapse Analytics**
   - Utilized as an integrated analytics service to accelerate insights from data warehouses and big data systems.
5. **Power BI**
   - Provides interactive data visualization and business intelligence capabilities.
  
## Data Model
<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Data%20Model.png">

1. **Data Ingestion**
   - Data ingestion from the on-premises SQL server to Azure SQL is accomplished via Azure Data Factory. The process involves:
   - Installation of Self-Hosted Integration Runtime.
   - Establishing a connection between Azure Data Factory and the local SQL Server.
   - Setting up a copy pipeline to transfer all tables from the local SQL server to the Azure Data Lake's "silver" folder.
<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Data%20Ingestion.png">

2. **Data Transformation**
   - After ingesting data into the "silver" folder, it is transformed following the medallion data lake architecture (silver, gold). Data transitions through silver, and ultimately gold, suitable for business reporting      tools like Power BI.
   - Azure Databricks, using PySpark, is used for these transformations. Data initially stored in parquet format in the "silver" folder is converted to the delta format as it progresses to "gold." This                       transformation is carried out through Databricks notebooks:
   * Mount the storage.
   * Transform data from "silver" to "gold" layer.

<video width="640" height="360" controls>
  <source src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Data%20Cleaning%20in%20Databricks.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Azure Data Factory is updated to execute the "silver" to "gold" notebooks automatically with each pipeline run.

<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Data%20pipeline.png">

  
3. **Data Loading**
Data from the "gold" folder is loaded into the Business Intelligence reporting application, Power BI. Azure Synapse is used for this purpose. The steps involve:

* Creating a link from Azure Storage (Gold Folder) to Azure Synapse.
* Writing stored procedures to extract table information as a SQL view.
* Storing views within a server-less SQL Database in Synapse.
<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Azure%20Synapse%20pipeline.png">


4: **Data Reporting**
Power BI connects directly to the cloud pipeline using DirectQuery to dynamically update the database. A Power BI report is developed to visualize AdventureWorks dataset data, including sales, product information, and customer gender.
