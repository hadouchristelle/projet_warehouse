# projet_warehouse
Building  data warehouse with Sql server, including ETL processes, data modeling and analytics.

## Project Requirements
This project implemented a three-layer data warehouse pipeline (Bronze, Silver, Gold) using SQL Server.
Data from folder file CRM and ERP systems was ingested  into the Bronze layer, cleaned and standardized in the Silver layer, and transformed into star-schema models in the Gold layer.

### Specifications
- **Data Sources**: Import data from two source systems (ERP and CRM) provided as CSV files.
- **Data Quality**: Cleanse and resolve data quality issues prior to analysis.
- **Integration**: Combine both sources into a single, user-friendly data model designed for analytical queries.
- **Scope**: Focus on the latest dataset only; historization of data is not required.

#### Project Architecture
The project architecture is based on a three-tiered approach (Bronze, Silver, Gold) to structure the ingestion, transformation, and exposure of data within a data warehouse.
<img width="1412" height="737" alt="image" src="https://github.com/user-attachments/assets/51c136b0-0d45-40b6-937e-523b4216e465" />

#### 1. loading file into layer bronze
Data from CRM and ERP folders containing CSV files are ingested into the Bronze layer, where they are stored as is in tables(bronze.crm_customer,bronze.crm_prodoc,bronze.crm_sales,bronze.epr_cust,bronze.epr_loc,bronze.epr_px), via a full load batch loading (truncate & insert), without transformation.
##### a-1: Table creation and data type definition
<img width="1913" height="808" alt="image" src="https://github.com/user-attachments/assets/4d1168ef-9249-48d6-93a3-bd799d219d15" />

##### a-1.2 load the data 
<img width="1911" height="798" alt="image" src="https://github.com/user-attachments/assets/faf1df6c-65a7-4f1a-80f2-6efb7a70a9d4" />


#### 2. Make the transformations and cleaning, and load the data into the silver layer.
In the Silver layer, data is cleaned, standardized, normalized, and enriched to ensure its quality and consistency.
##### a.2.1 Transformation in the bronze.crm_customer and load the data into the silver.crm_customer table
        -Normalize marital status values to readable format
        -Normalize gender values to readable format
        -renove unwanted space
<img width="1723" height="853" alt="image" src="https://github.com/user-attachments/assets/5ecb86e7-0d17-41f5-a51e-50a41c018ee9" />
##### a-2.2 transformation in the bronze.crm_prodoc and load the data into the silver.crm_prodoc
<img width="1881" height="738" alt="image" src="https://github.com/user-attachments/assets/eb15e15a-f5c3-4ef8-ab0c-a528c8fd5e04" />

##### a-2.3 transformation in the bronze.crm_sales and load the data into the silver.sales
<img width="1898" height="847" alt="image" src="https://github.com/user-attachments/assets/82fa579c-bff1-4eaa-972c-511a1ad1e88b" />





