# End-to-end-Data-Engineer-Project-E-commerce
## Project Description:
This project focuses on building an efficient data pipeline tailored for e-commerce, handling diverse datasets from various sources. We start by extracting data from CSV files, followed by light transformations using Alteryx. The cleaned data is then loaded into SQL Server for staging, where it undergoes further transformations with Power Query to prepare it for deeper analysis. The refined data is modeled in SQL Server to establish relationships and structure, setting the stage for powerful reporting.

The final step involves leveraging Power BI for insightful data visualization, creating interactive dashboards that provide key business metrics and trends. This end-to-end solution not only streamlines the data processing workflow but also delivers meaningful insights, helping businesses make informed, data-driven decisions.
## Project Architecture:

<img src="https://github.com/Dharmil290998/End-to-end-Data-Engineer-Project-E-commerce/blob/main/Project%20Flow.png">

## Current Environment
* Utilized the E-commerce dataset from Microsoft.
* Set up an on-premises Microsoft SQL server on a personal computer.
* Imported the dataset using Microsoft SQL Server Management Studio.
* Created a new user profile, "ndp."
* Saved "ndp" profile's password credentials as a Secret in Azure Key Vault.
