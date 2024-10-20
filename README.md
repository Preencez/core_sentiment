﻿# core_sentiment_dag
This project uses Apache Airflow to orchestrate a data pipeline for downloading, processing, and loading Wikipedia pageview data into a PostgreSQL database. The pipeline tracks daily pageviews for several major companies.

Project Overview
The pipeline performs the following tasks:

Download Pageviews: Fetch Wikipedia pageview data for a specified date.
Extract Data: Unzip the downloaded .gz file.
Process Data: Parse the pageview data to track views for companies like Amazon, Google, and Microsoft.
Load Data: Store the processed data into a PostgreSQL table for further analysis.
DAG Structure
The DAG includes the following tasks:

download_pageviews: Downloads gzipped pageview data from Wikipedia.
extract_pageviews: Extracts the downloaded file.
process_pageviews: Filters pageview data for selected companies.
load_into_postgres: Loads processed data into a PostgreSQL database using PostgresHook.
Prerequisites
Airflow
PostgreSQL (set up with a connection in Airflow)
Python packages: requests, psycopg2
Usage
Clone the repository.
Set up the required dependencies and ensure PostgreSQL is running.
Define a connection in Airflow with the ID postgres_default to your PostgreSQL instance.
Trigger the DAG through the Airflow UI.
