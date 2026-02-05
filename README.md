# Azure Data Factory – AdventureWorks ETL Project

## Project Overview
This project demonstrates an end-to-end ETL pipeline built in Azure Data Factory to transform raw sales data into a structured relational data model for analytical use.

The solution ingests a flat sales dataset and splits it into normalized business entities such as customers, products, orders, and sales details.

## Architecture

Source  
AdventureWorks raw dataset stored as a CSV file in Azure Blob Storage.

Processing Layer (ADF Dataflows)  
Multiple mapping dataflows are used to clean, transform, deduplicate, and structure the data into relational entities.

Destination  
Azure SQL Database containing the final structured tables:
- Person  
- Customer  
- CustomerAddresses  
- Product  
- Sale  
- SaleDetails  

The pipeline orchestrates the execution order to respect relational dependencies.

## Dataflows Description

DF_SplitAndLoad_Person – Extracts and merges customer and salesperson identities into the Person table  
DF_Load_Customer – Builds the Customer entity linked to Person  
DF_Load_CustomerAddresses – Loads customer address records  
DF_Load_Product – Extracts and deduplicates product information  
DF_Load_SaleHeader – Creates order-level sales records  
DF_Load_SaleDetails – Loads line-level sales transaction details  

## Key Transformations
- Column selection and mapping  
- Union of multiple entity types  
- Deduplication using aggregations  
- Joins between entities to create surrogate relationships  
- Data type casting and schema alignment  

## Skills Demonstrated
- Azure Data Factory pipeline orchestration  
- Mapping Dataflows for ETL transformations  
- Cloud data ingestion from Blob Storage  
- Loading structured data into Azure SQL Database  
- Relational data modeling principles  

## Technologies Used
- Azure Data Factory  
- Azure Blob Storage  
- Azure SQL Database  
- SQL-based data modeling concepts
