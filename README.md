# Udacity Data Engineer Nanodegree Project 1

The objective is to build an automated ETL pipeline with Apache Airflow to analyze the data that's collected on songs and user activity on a new music streaming app, particularly what songs users are listening to.

## Getting Started

### Prerequisites

```
Python 3.6
Airflow 1.10
```

You need to have an AWS Redshift Cluster up and running and an IAM role associated with it with the _correct_ permissions `AmazonS3ReadOnlyAccess, AmazonRedshiftFullAccess`. 

Tables must be created in Redshift before running Airflow. The create table SQL statements can be found in: `create_tables.sql`

## Data Sources

Data resides in two directories that contain files in JSON format:

1. Log data: s3://udacity-dend/log_data
2. Song data: s3://udacity-dend/song_data

## Data Quality Checks

To ensure the tables were loaded properly, a data quality check is performed to count the total records of each table. If a table has no rows then the workflow will fail and throw an error message.
