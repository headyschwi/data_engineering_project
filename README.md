# End-to-End Data Engineering Project

This project demonstrates an end-to-end data engineering pipeline, starting from data extraction from a local SQL Server to visualization in Power BI. The pipeline includes data transformation across multiple layers using Azure Data Factory.

## Project Overview

### Architecture
![image](https://github.com/user-attachments/assets/7a8f2559-2914-42ac-9425-da69e89e18ba)

The pipeline consists of the following stages:

1. **Data Source (Local SQL Server)**  
   - Data originates from a local SQL Server database.

2. **Extraction (Azure Data Factory)**  
   - Azure Data Factory (ADF) is used to extract data from the local SQL Server to Azure.

3. **Transformation and Loading (Databricks & Data Lake Layers)**  
   Data is transformed and loaded into three distinct layers using Databricks:
   - **Bronze Layer:** Raw data is ingested with minimal transformation.
   - **Silver Layer:** Data is cleaned and enriched for analytical purposes.
   - **Gold Layer:** Fully transformed and aggregated data, ready for reporting and advanced analytics.

4. **Visualization (Power BI)**  
   - Final data is visualized using Power BI for business insights and reporting.

## Technology Stack

- **SQL Server (Local):** Data source.
- **Azure Data Factory (ADF):** Data extraction and pipeline orchestration.
- **Databricks:** Data transformation and loading into Azure Data Lake.
- **Azure Data Lake:** Storage for raw, cleaned, and processed data.
- **Power BI:** Data visualization and reporting.

## Data Pipeline
![image](https://github.com/user-attachments/assets/3a135c84-54a4-48af-b28a-386455166487)

## Power BI Visualization
![image](https://github.com/user-attachments/assets/5fe34b2a-b84f-44bf-bbc7-59caf84a3df8)

## Installation

Follow these steps to set up the pipeline:

1. **SQL Server Setup:**
   - Ensure the local SQL Server is accessible.
   - Configure firewall rules and permissions to allow Azure Data Factory to connect.

2. **Data Lake:**
   - Set up the storage account and create three layers: `Bronze`, `Silver`, and `Gold`.

3. **Azure Data Factory:**
   - Create a new ADF instance in the Azure portal.
   - Configure Linked Services for the local SQL Server and Azure Data Lake.
   - Define datasets for source and destination.
   - Create a pipeline to extract data and load it into the Bronze layer of the Data Lake.

4. **Databricks Setup:**
   - Create a Databricks workspace.
   - Configure a cluster to run transformations.
   - Develop notebooks for:
     - Bronze → Silver transformations (data cleaning and enrichment).
     - Silver → Gold transformations (aggregation and final business logic).
   - Use Databricks jobs to schedule and orchestrate transformations.

5. **Power BI:**
   - Connect Power BI to the Gold layer of the Data Lake.
   - Design the necessary dashboards and reports for data visualization.

## Usage

1. Run the Azure Data Factory pipeline to extract data into the `Bronze` layer.
2. Use Databricks to transform and move data through the `Bronze`, `Silver`, and `Gold` layers.
3. Verify the data at each layer.
4. Use Power BI to visualize data from the `Gold` layer.

## Project Structure

```plaintext
├── data_engineering_project/
│   ├── Pipeline-ADF/         # Azure Data Factory pipeline files
│   ├── Notebooks-Databricks/ # Databricks notebooks for data transformation
│   ├── PowerBI/              # Power BI dashboard files
│   └── README.md             # Project documentation
```