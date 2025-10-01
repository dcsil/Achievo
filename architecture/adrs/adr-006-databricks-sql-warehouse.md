# ADR 006: Databricks SQL Warehouse

**Date:** 2025-09-30 \
**Status:** Proposed  

## Context  
Our scheduling app requires a backend capable of handling structured syllabus data, and supporting fast queries for deadlines, tasks, and progress tracking.  

## Decision  
We will use Databricks SQL Warehouse to store and query structured scheduling data, providing both reliable transactional access and scalable analytics.  

## Consequences 
- **Positive:**  
- High-performance querying and analytics at scale.  
- Unified platform for data storage, AI, and reporting.  
- Simplifies querying across structured data.

- **Negative:** 
- None of our members have prior experience working with it, so potential learning curve.
- We only have access to the free version, and there could be some limitations 

## Alternatives Considered  
- **Option A: MySQL**
    - Pros: Reliable, widely used relational database with strong community support. 
    - Cons: Limited scalability for large-scale analytics compared to data warehouses.
- **Option B: BigQuery**
    - Pros: Aligned with the rest of our project, since we are using Google services for other areas (Vertex AI, building a Chrome extension)
    - Cons: More limited features in free version

## References 
- [Connect to a SQL warehouse — Databricks docs](https://docs.databricks.com/aws/en/compute/sql-warehouse/?utm_source=chatgpt.com)
- [Data warehousing on Databricks / Databricks SQL overview](https://docs.databricks.com/aws/en/sql/?utm_source=chatgpt.com)
- [MySQL limitations in big data / analytics use cases](https://www.gridgain.com/resources/blog/mysql-limitations-in-big-data-analytics?utm_source=chatgpt.com)
- [BigQuery Pricing](https://cloud.google.com/bigquery/pricing?hl=en#:~:text=BigQuery%20charges%20for%20other%20operations,billing%20account%20attached%20to%20it.)