---
title : "Resources"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Download the Lambda Function
For this workshop, you'll need a specific Lambda function to process the incoming data. 

Download the [upload-data.zip](./upload-data.zip) file which contains the `lambda.py` essential for our tasks.

#### Contents of `lambda.py`

```python
import boto3
import requests
from requests_aws4auth import AWS4Auth
import os
import json
import datetime

region = 'ap-southeast-1'
service = 'es'
credentials = boto3.Session().get_credentials()
awsauth = AWS4Auth(credentials.access_key, credentials.secret_key, region, service, session_token=credentials.token)

index = 'lambda-s3-index'
type = '_doc'
host = os.environ['ES_DOMAIN_URL']
url = host + '/' + index + '/' + type

headers = { "Content-Type": "application/json" }

s3 = boto3.client('s3')
bucket = os.environ['S3_BUCKET']

# Lambda execution starts here
def handler(event, context):
    
    sensorID = event['sensorID']
    timestamp = datetime.datetime.now().strftime("%Y%m%d%H%M%S")
    temperature = event['temperature']
        
    document = { "sensorID": sensorID, "timestamp": timestamp, "temperature": temperature }
    print(document)
    # post to S3 for storage
    s3.put_object(Body=json.dumps(document).encode(), Bucket=bucket, Key=sensorID+"-"+timestamp+".json")
    # post to amazon elastic search for indexing and kibana use
    r = requests.post(url, auth=awsauth, json=document, headers=headers)
    print(r)
    print(url)
    response = "Data Uploaded"
    return {
        "Response" : response,
        "sensorID" : sensorID,
        "temperature": temperature
    }

```