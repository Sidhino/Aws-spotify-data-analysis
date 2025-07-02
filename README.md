
## AWS-Based Data Analysis Pipeline using Glue, Athena, and Python



## Description
This project demonstrates how to build a serverless data lake architecture on AWS to analyze sales data. Using Amazon S3 for storage, AWS Glue for data cataloging, Amazon Athena for querying, this project provides a scalable and cost-effective way to analyze structured data in the cloud.

## Architecture Overview / Workflow
[CSV Dataset] → [S3 Bucket]
                     ↓
              [Glue Crawler]
                     ↓
              [Glue Data Catalog]
                     ↓
               [Athena Queries]
                     ↓
           [Python (Optional Analysis)]

## Services used
List and briefly describe each AWS service used:

S3 – To store the raw dataset.

Glue Crawler – To infer schema and populate the Glue Data Catalog.

Glue Job – (if used) for transformations or ETL.Database, Glue Catalog DB

Athena – To run SQL queries directly on the S3 data.

IAM – (optional) for managing access roles.
## Steps to Reproduce / Run the Project 
1.Upload CSV to Amazon S3

2.Create a Glue Crawler

3.Target: S3 path above

4.Run the Crawler

 Confirm that the table appears with the correct schema.

5.Query with Athena




## Requirments
 Baisc knowledge of AWS (IAM, S3 bucket,Glue,Athena,)





