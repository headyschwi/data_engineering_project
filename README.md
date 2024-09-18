# End-to-End Data Engineering Project

This project demonstrates an end-to-end data engineering pipeline, starting from extracting data from an on-premise SQL Server to visualizing it in Power BI. The pipeline includes the transformation of data across multiple layers using Azure Data Factory.

## Project Overview

### Architecture
![image](https://github.com/user-attachments/assets/b4f93f3c-bd6e-48f2-8fef-594c25038c2e)

The pipeline consists of the following steps:

1. **Data Source (SQL Server On-Premise)**  
   - Data is sourced from an on-premise SQL Server database.

2. **Extraction (Azure Data Factory)**  
   - Azure Data Factory (ADF) is used to extract the data from the on-premise SQL Server to Azure.
   
3. **Transformation and Loading (Databricks & Data Lake Layers)**  
   The data is transformed and loaded into three distinct layers using Databricks:
   - **Bronze Layer:** Raw data is ingested into this layer with minimal transformation.
   - **Silver Layer:** The data is cleaned and enriched, making it suitable for analysis.
   - **Gold Layer:** This layer contains fully transformed and aggregated data, ready for reporting and advanced analytics.

4. **Visualization (Power BI)**  
   - The final data is visualized using Power BI for business insights and reporting.

## Technology Stack

- **SQL Server (On-Premise):** Data source.
- **Azure Data Factory (ADF):** Data extraction and pipeline orchestration.
- **Databricks:** Data transformation and loading into the Azure Data Lake.
- **Data Lake (Azure):** Storage for the raw, cleaned, and processed data.
- **Power BI:** Visualization and reporting.

## Installation

To set up this pipeline, follow these steps:

1. **SQL Server Setup:**
   - Ensure that the on-premise SQL Server is accessible.
   - Configure the necessary firewall rules and permissions for Azure Data Factory to connect.

2. **Data Lake:**
   - Set up the storage account and create three layers: `Bronze`, `Silver`, and `Gold`.

3. **Azure Data Factory:**
   - Create a new ADF instance in the Azure portal.
   - Set up the Linked Services for the on-premise SQL Server and the Azure Data Lake.
   - Define datasets for the source and destination.
   - Create the pipeline to extract data and load it into the Data Lake's Bronze layer.

4. **Databricks Setup:**
   - Create a Databricks workspace.
   - Set up a cluster to run transformations.
   - Develop notebooks for the following:
     - Bronze to Silver transformations (data cleaning and enrichment).
     - Silver to Gold transformations (aggregation and final business logic).
   - Use Databricks jobs to schedule and orchestrate the transformations.

5. **Power BI:**
   - Connect Power BI to the Gold layer of the Data Lake.
   - Design the necessary reports and dashboards for data visualization.

## Usage

1. Run the Azure Data Factory pipeline to extract the data into the `Bronze` layer.
2. Use Databricks to transform and move data through the `Bronze`, `Silver`, and `Gold` layers.
3. Verify the data in each layer.
4. Use Power BI to visualize the data from the `Gold` layer.

## Project Structure

```plaintext
├── data-engineering-project/
│   ├── ADF-Pipeline/         # Azure Data Factory pipeline files
│   ├── Databricks-Notebooks/ # Databricks notebooks for data transformation
│   ├── PowerBI/              # Power BI dashboard files
│   └── README.md             # Project documentation
```
