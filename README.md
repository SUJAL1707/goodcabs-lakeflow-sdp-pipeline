# Goodcabs: Regional Analytics Pipeline with Databricks Lakeflow SDP

An end-to-end data engineering project that builds a medallion-architecture
(bronze → silver → gold) pipeline on Databricks Free Edition using
Lakeflow Spark Declarative Pipelines (SDP).

> using Databricks Free Edition | Spark Declarative Pipelines".

## Business Problem
Goodcabs is a cab-service company operating across multiple Indian cities.
Regional managers received late, generic dashboards and had to rework data
manually. This project delivers timely, city-specific data views.

## Architecture


Source CSVs (Amazon S3) → Bronze → Silver → Gold → city-specific views

## Tech Stack
- Databricks Free Edition
- Lakeflow Spark Declarative Pipelines (Python + SQL)
- Delta Lake, Unity Catalog
- Amazon S3 (source storage)
- Auto Loader (incremental ingestion)

## Data Model
- **city** (dimension): city_id, city_name
- **trips** (fact): trip_id, date, city_id, fare, distance, ratings, ...
- **calendar** (dimension): date, year, month, quarter, weekday/weekend, holiday

## Pipeline Layers
| Layer | Tables | What happens |
|---|---|---|
| Bronze | city, trips | Raw ingestion + metadata columns |
| Silver | city, trips, calendar | Cleaning, renaming, data quality checks, CDC upserts |
| Gold | fact_trips + city views | Joined, denormalized table and per-city views |

## Key Features


## Project Structure


## How to Run
1. [Create a Databricks Free Edition account]
2. [Set up S3 bucket and external location]
3. [Run setup notebook, then the pipeline]

## Results and Screenshots


## What I Learned


## Credits
