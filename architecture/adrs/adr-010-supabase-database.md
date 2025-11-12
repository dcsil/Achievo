# ADR 010: Supabase Postgres Database

**Date:** 2025-11-12 \
**Status:** Accepted

## Context  
Our scheduling app requires a backend capable of handling structured syllabus data, and supporting fast queries for deadlines, tasks, and progress tracking. 

## Decision  
After initial implementation with Databricks SQL Warehouse ([ADR 006](./adr-006-databricks-sql-warehouse.md)), we realized it had too much overhead for simple queries, so we decided to migrate over to Supabase. Supabase will now be used to store and gather task, assignment, reward and user information.
 
## Consequences 
- **Positive:**  
  - Postgres is widely adopted and a relational database.
  - More intuitive dashboard for adding and modifying data.
  - Simple permission sharing and lower learning curve.

- **Negative:** 
  - No prior experience with Supabase specifically.
  - Less optimized for very largescale workloads.
  - Migration effort to switch from Databricks to Supabase.

## Alternatives Considered  
- **Option A: Databricks SQL Warehouse (PREVIOUS)**:
  - Pros: High-performance analytics, unified platform for data and AI, scalable for large datasets.
  - Cons: Steep learning curve, limited free tier features, overkill for transactional workload, high overhead for queries.
- **Option B: MySQL**
  - Pros: Reliable, widely used relational database with strong community support. 
  - Cons: Limited scalability for large-scale analytics compared to data warehouses.
- **Option C: BigQuery**
  - Pros: Aligned with the rest of our project, since we are using Google services for other areas (Vertex AI, building a Chrome extension)
  - Cons: More limited features in free version

## References 
- [Supabase docs](https://supabase.com/docs)
- [Connect to a SQL warehouse — Databricks docs](https://docs.databricks.com/aws/en/compute/sql-warehouse/?utm_source=chatgpt.com)
- [Data warehousing on Databricks / Databricks SQL overview](https://docs.databricks.com/aws/en/sql/?utm_source=chatgpt.com)
- [MySQL limitations in big data / analytics use cases](https://www.gridgain.com/resources/blog/mysql-limitations-in-big-data-analytics?utm_source=chatgpt.com)
- [BigQuery Pricing](https://cloud.google.com/bigquery/pricing?hl=en#:~:text=BigQuery%20charges%20for%20other%20operations,billing%20account%20attached%20to%20it.)
