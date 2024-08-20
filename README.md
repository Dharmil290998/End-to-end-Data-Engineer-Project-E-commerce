# End-to-end-Data-Engineer-Project-E-commerce
## Project Description:
This project focuses on building an efficient data pipeline tailored for e-commerce, handling diverse datasets from various sources. We start by extracting data from CSV files, followed by light transformations using Alteryx. The cleaned data is then loaded into SQL Server for staging, where it undergoes further transformations with Power Query to prepare it for deeper analysis. The refined data is modeled in SQL Server to establish relationships and structure, setting the stage for powerful reporting.

The final step involves leveraging Power BI for insightful data visualization, creating interactive dashboards that provide key business metrics and trends. This end-to-end solution not only streamlines the data processing workflow but also delivers meaningful insights, helping businesses make informed, data-driven decisions.
## Project Architecture:

<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Project%20Flow.png">
1. Data is ingested and orchestrated using Azure Data Factory.
2. Raw data is stored in the <b>Silver layer</b> of Azure Data Lake Storage Gen2.
3. Data is processed and cleansed using Azure Databricks, with results stored in the Silver layer.
4. Further transformations and analytics are performed, producing business-ready data in the Gold layer.
5. Azure Synapse Analytics is used for large-scale data warehousing and analytics.
6. Final insights are visualized using Power BI.
   
## Current Environment
* Utilized the E-commerce dataset from Microsoft.
* Set up an on-premises Microsoft SQL server on a personal computer.
* Imported the dataset using Microsoft SQL Server Management Studio.
* Created a new user profile, "ndp."
* Saved "ndp" profile's password credentials as a Secret in Azure Key Vault.

<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/on-premises%20Microsoft%20SQL%20server.png">

## Azure Technologies Used

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
