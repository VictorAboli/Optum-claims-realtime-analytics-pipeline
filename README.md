## About This Project

A real-time end-to-end data analytics pipeline built for Optum 
healthcare claims data. This project simulates a production-grade 
data engineering workflow covering data ingestion, stream processing, 
storage, cleaning, transformation, and reporting.

The pipeline ingests raw EDI 837 (medical claims), EDI 835 
(remittance), member enrollment, and provider network data through 
Apache Kafka topics, land them into Microsoft SQL Server raw staging 
tables via a Python consumer, and applies a full SQL-based cleaning 
and a transformation layer to produce analysis-ready data.

## Key Features

- Real-time streaming ingestion using Apache Kafka (KRaft mode, no Zookeeper)
- Python producer and consumer scripts for all 4 claims data sources
- Microsoft SQL Server as the data warehouse (raw + clean layers)
- Full data cleaning covering deduplication, null handling, 
  date format standardisation, and invalid value correction
- Bronze → Silver data layer architecture
- Healthcare-specific KPIs: denial rate, cost PMPM, 
  turnaround time, provider scorecard
- Scalable pipeline design following Optum Data Analyst standards

## Tech Stack

- Apache Kafka 7.6 (KRaft mode)
- Python 3.9+ (kafka-python, pyodbc, pandas)
- Microsoft SQL Server 17
- Docker (Kafka + Kafka UI)
- SQL Server Management Studio (SSMS)
- Tableau / Power BI (reporting layer)

## Pipeline Architecture

Raw CSV Files → Kafka Producer → Kafka Topics → Kafka Consumer 
→ SQL Server Raw Tables → SQL Cleaning → Clean Tables → Dashboard
