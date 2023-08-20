---
title : "Opensearch Service"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Building a Data Lake with Amazon OpenSearch Service

#### Objective
In this workshop, participants will learn how to construct an AWS-based data lake to monitor and analyze water temperatures from various water bodies. By leveraging AWS services, we'll create a seamless flow from data collection to analysis

#### Scenario:
Your organization is keen on monitoring water temperatures from lakes, ponds, and streams in the vicinity. Sensors have been deployed across these water bodies, capable of making HTTPS calls to transmit data, including sensor ID and temperature readings. These sensors are programmed to send data every 15 minutes.

#### Brief Overview
In this workshop, participants will embark on a journey to create a comprehensive system that ingests, stores, and analyzes water temperature data from sensors deployed across different water bodies. Leveraging key AWS services, we'll ensure efficient data flow, storage, and analysis.

![ConnectPrivate](/images/Architecture.png) 

#### Key Components:
- **Amazon S3:** Primary data storage layer.
- **Amazon OpenSearch Service:** For data indexing and searching.
- **Amazon API Gateway & AWS Lambda:** Data ingestion and processing pipeline.

#### Content
 1. [Introduction ](1-introduce/)
 2. [Preparation](2-prerequiste/)
 3. [Creating an Amazon OpenSearch Service cluster](3-amazon-opensearch-service)
 4. [Creating an S3 bucket](4-s3-bucket/)
 5. [Setting Up AWS Lambda Function](5-lambda/)
 6. [Modify S3 and OpenSearch Policy for Lambda access](6-modify-s3-and-aoi-policy/)
 7. [Adding Environment Variables to the Lambda Function](7-vdding-var-lambda/)
 8. [Creating a REST API and Checking Solution](8-create-api-gateway-and-checking)
 9. [Clean up resources](9-clean-up)

#### Duration:
Approximately 35 minutes
