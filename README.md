# YouTube Trending Data Pipeline | AWS Data Engineering Project

## Overview
This project aims to securely manage, streamline, and perform analysis on structured and semi-structured YouTube videos data, focusing on video categories and trending metrics. It demonstrates how to design a scalable data engineering pipeline on AWS to convert raw datasets into meaningful insights.

## Architecture Diagram
![Project Architecture.](architecture.jpeg)

The architecture includes the following components:
- Data Source → YouTube Trending Dataset (Kaggle CSV + JSON metadata).
- Ingestion → Upload raw data files into Amazon S3 bucket.
- Data Cataloging → Use AWS Glue Crawler to detect schema and build a data catalog.
- ETL / Transformation → Run AWS Glue Jobs (PySpark scripts) to clean, standardize, and enrich the dataset.
- Event-driven Processing → AWS Lambda functions trigger additional processing or automation when new data lands in S3.
- Centralized Storage → Store both raw and transformed datasets in Amazon S3 (Data Lake).
- Query & Analysis → Use AWS Athena to run SQL queries directly on transformed data in S3.
- Visualization → Connect Athena with Amazon QuickSight to build dashboards and analyze metrics like views, likes, and trending patterns.
- Security & Access Control → AWS IAM manages permissions for services, roles, and users.

## Services Used
- Amazon S3: Store raw and transformed datasets in a central data lake.
- AWS IAM: Enforce secure and role-based access to pipeline components.
- AWS Glue: Automate data discovery and perform ETL transformations.
- AWS Lambda: Trigger lightweight processing tasks without managing servers.
- AWS Athena: Run SQL queries directly on S3 data for fast analysis.
- Amazon QuickSight: Create BI dashboards to interpret and present results.

## Dataset
The project relies on the Kaggle YouTube Trending Dataset, which tracks daily trending videos across countries. It includes video details (title, channel, publish time, tags), engagement stats (views, likes, dislikes, comments), and region-specific categories linked through JSON metadata.

Dataset: [YouTube Trending Dataset on Kaggle](https://www.kaggle.com/datasets/datasnaek/youtube-new)

## Getting Started
### Prerequisites
- AWS account with access to S3, Glue, Lambda, Athena, QuickSight
- Python & SQL basics
- Kaggle account for downloading the dataset

### Setup Steps

1. Clone this repository locally.
2. Download the Kaggle dataset and upload it to your S3 bucket.
3. Configure IAM roles for Glue, Lambda, and Athena.
4. Run Glue crawlers to catalog the dataset.
5. Create and execute ETL jobs for cleaning and transformation.
6. Query processed data in Athena.
7. Connect Athena output to QuickSight and build dashboards.

## Resources
- [AWS Account Setup](https://aws.amazon.com/premiumsupport/)
- [Download AWS CLI](https://aws.amazon.com/cli/)
