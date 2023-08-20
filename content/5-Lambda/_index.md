---
title : "Setting Up AWS Lambda Function"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
#### Introduction

AWS Lambda is a serverless compute service that lets you run code without provisioning or managing servers. In this guide, we'll walk through the steps to set up an AWS Lambda function to process our data.

#### Step-by-Step Guide to Create an AWS Lambda Function

1. **Access the AWS Lambda Console**: Navigate to the [AWS Lambda dashboard](https://console.aws.amazon.com/lambda/).

   ![Lambda Dashboard](/images/5.lambda/01-lambda.png)

2. **Initiate Function Creation**: Click on **Create function**.

   ![Create Function](/images/5.lambda/02-lambda.png)

3. **Function Configuration**:
   - **Author from scratch**: Keep this option selected
   - **Name**: Provide a name for your Lambda function (e.g., `upload-data`).
   - **Runtime**: Select the latest supported version of Python
   - **Permissions**: Expand Change default execution role
   - **Execution role**: Use an existing role
   - **Existing role**: data-lake

   ![Function Configuration](/images/5.lambda/03-lambda.png)


4. **Set up Lambda**:
   - **Upload code**: If you have a `.zip` file (like the `upload-data.zip`), choose "Upload a .zip file" and upload your file.   
   ![Function Code](/images/5.lambda/04-lambda.png)

   - **Set region**: Set value of **region** to your current region you practice the lab (e.g. ap-southeast-1)
   ![Function Code](/images/5.lambda/05-lambda.png)

   - **Runtime settings**: Scroll to Runtime settings and choose Edit then
   ![Function Code](/images/5.lambda/06-lambda.png)

      In the Handler box, replace the existing value with `lambda.handler` and choose Save.
   ![Function Code](/images/5.lambda/07-lambda.png)

   - **Environment Variables**: Choose the Configuration tab, choose Environment variables and then choose Edit.
   ![Environment Variables](/images/5.lambda/08-lambda.png)

      Choose Add environment variable and configure the following settings. 
         Key: `S3_BUCKET`
         Value: Paste your bucket name (e.g., `datalakes-workshop1`)
   ![Environment Variables](/images/5.lambda/09-lambda.png)

   - **Amazon Resource Name**: In the Configuration tab menu, choose Permissions. Under Role name, choose the **data-lake** link.
   ![Amazon Resource Name](/images/5.lambda/10-lambda.png)

      Copy the role Amazon Resource Name (ARN), we'll use it in future sections.
   ![Amazon Resource Name](/images/5.lambda/11-lambda.png)

#### Conclusion

With the AWS Lambda function now set up, you're equipped to process and ingest data into your data lake. In the upcoming sections, we'll delve into integrating this function with our Amazon S3 bucket and Amazon OpenSearch Service.

