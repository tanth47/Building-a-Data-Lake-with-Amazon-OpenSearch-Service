---
title: "Test the Solution"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 8.2 </b> "
---

#### Checking OpenSearch Service for Data

In this segment, we'll utilize the OpenSearch Service domain to search for the ingested data.

1. Retrieve the **OpenSearch Service domain URL** you saved earlier.For example:
```https://search-water-temp-5sgqhr6nez5dilp6icwb5n4zhu.ap-southeast-1.es.amazonaws.com```

2. Open a new browser tab and input the URL, appending `/lambda-s3-index/_search?pretty`.
   ![OpenSearch Service Search](/images/8.api-and-check/8.2.check/01-check.png)

3. (Optional) Execute more tests in the API Gateway. For Example:
   ```json
   {
     "sensorID" : "0028",
     "temperature" : "02"
   }
   ```
5. Navigate to the **Amazon S3 console** and access your bucket. You should spot several `.json` files. Download one to inspect its content.
   ![Amazon S3 Bucket Content](/images/8.api-and-check/8.2.check/02-check.png)

#### Conclusion

You've successfully tested the solution, ingesting data into OpenSearch Service and verifying its existence in the Amazon S3 bucket.

