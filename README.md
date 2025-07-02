
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


## Test Cases
1.Top 10 Tracks by Track Popularity

SELECT track_name, artist_id, track_popularity
FROM your_table_name
WHERE track_popularity IS NOT NULL
ORDER BY CAST(track_popularity AS INT) DESC
LIMIT 10;

2.Most Popular Albums by Album Popularity

SELECT album_name, album_id, MAX(CAST(album_popularity AS INT)) AS popularity
FROM your_table_name
GROUP BY album_name, album_id
ORDER BY popularity DESC
LIMIT 10;

3.-- Distribution of Track Popularity (Buckets)

SELECT 
  CASE 
    WHEN CAST(track_popularity AS INT) BETWEEN 0 AND 20 THEN '0-20'
    WHEN CAST(track_popularity AS INT) BETWEEN 21 AND 40 THEN '21-40'
    WHEN CAST(track_popularity AS INT) BETWEEN 41 AND 60 THEN '41-60'
    WHEN CAST(track_popularity AS INT) BETWEEN 61 AND 80 THEN '61-80'
    WHEN CAST(track_popularity AS INT) BETWEEN 81 AND 100 THEN '81-100'
    ELSE 'Unknown'
  END AS popularity_range,
  COUNT(*) AS track_count
FROM data_warehouse
GROUP BY 1
ORDER BY 1;

