# Nyc-DE-Project
City of New York Data

NYC 311 Lakehouse Pipeline
An end-to-end data engineering pipeline built using PySpark and Delta Lake, following the Medallion Architecture (Bronze, Silver, Gold).

Architecture Overview
Bronze Layer: Ingests raw JSON data from the NYC Open Data (311 Service Requests) API.
Silver Layer: Cleans data, casts types, and handles incremental Upserts (MERGE INTO) to manage duplicate API pulls. Physically optimized using ZORDER.
Gold Layer: Aggregates response times and complaint volumes by borough for downstream BI tools.
Tech Stack
Compute: Databricks (Spark)
Storage: Delta Lake
Language: Python / PySpark
Key Optimizations Implemented
Upserts (Merge): Handled incremental loads gracefully without overwriting history.
Z-Ordering: Collocated data by incident_zip for faster spatial querying.
Vacuuming: Implemented storage management to clear stale file versions.
