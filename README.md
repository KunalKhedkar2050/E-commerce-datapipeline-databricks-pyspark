# Architecture Overview

The pipeline follows the Bronze, Silver, Gold architecture to manage data at different stages of processing:

## Bronze Layer (Raw Data)

This layer stores raw data from different data sources, such as transactional logs, product catalogs, and customer data, without any transformations or cleaning.  
Data is ingested in its native form (e.g., CSV, JSON, or Parquet) and stored in a scalable cloud data lake. This layer acts as the raw foundation for further transformations.

### Key Points:
- Ingest data from various sources.
- Raw, untransformed data is stored for auditing, historical reference, and traceability.

## Silver Layer (Cleaned & Transformed Data)

In this layer, the raw data from the Bronze layer is cleaned and transformed into a more structured form.

### Key Points:
- Data is cleaned, validated, and enriched (e.g., removing duplicates, filling missing values, adding computed columns).
- A more structured, consistent, and usable version of the data is created for further analysis.

## Gold Layer (Aggregated Business Insights)

This is the final layer where business logic is applied to aggregate, summarize, and perform analytics on the cleaned data.  
Aggregations like total sales per product, customer behavior analytics, and inventory forecasting can be performed here.  
Data in this layer is ready for visualization, reporting, and decision-making.

### Key Points:
- Aggregated and summarized data for business reporting (e.g., daily sales, customer trends).
- Provides clean, high-quality data ready for consumption by BI tools or decision-makers.

## Technologies Used

- **Databricks**: Cloud-based platform for running Spark-based workloads.
- **PySpark**: Python API for Apache Spark to handle large-scale data processing.
- **Delta Lake**: For managing data lakes with ACID transactions and scalable metadata handling.
- **Apache Spark**: Distributed computing system for large-scale data processing.
- **Azure**: Cloud storage (Blob Storage) for storing the raw and processed data.

## Features

- **Data Ingestion**: Collects raw transactional and product data from multiple sources.
- **Data Transformation**: Cleans and enriches raw data for business use.
- **Data Aggregation**: Computes business metrics such as total sales, user behavior, and product performance.
- **Scalable**: Designed for handling large amounts of data using Spark’s distributed computing capabilities.
