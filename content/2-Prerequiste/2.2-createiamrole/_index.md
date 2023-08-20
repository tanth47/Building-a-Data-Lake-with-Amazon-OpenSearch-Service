---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---
#### Introduction

To ensure smooth data ingestion into our data lake, we need to set up an IAM Role. This role will grant the necessary permissions for AWS services, such as Lambda, to interact with Amazon S3 and Amazon OpenSearch Service.

#### Step-by-Step Guide to Create the IAM Role

1. **Access IAM Management Console**: Navigate to the [IAM service administration interface](https://console.aws.amazon.com/iamv2/).

2. **Roles Section**: On the left navigation pane, select **Roles**.
   
   ![Roles Section](/images/2.prerequisite/2.2.iamrole/01-iamrole.png)

3. **Initiate Role Creation**: Click on **Create role**.
   
   ![Create Role](/images/2.prerequisite/2.2.iamrole/02-iamrole.png)

4. **Select Service**: Choose **AWS service**, followed by **Lambda** (since our Lambda function will be interacting with S3 and OpenSearch). Then, proceed by clicking **Next**.
   
   ![Select Service](/images/2.prerequisite/2.2.iamrole/03-iamrole.png)

5. **Search and Select Policies**: In the search bar, type `AmazonS3FullAccess` and select it. Next, search for `AmazonESFullAccess` and select it as well. Once both policies are selected, move to the next step by clicking **Next**.
   
   ![Select Policies](/images/2.prerequisite/2.2.iamrole/04-iamrole.png)
   ![Select Policies](/images/2.prerequisite/2.2.iamrole/05-iamrole.png)

6. **Name and Create the Role**: Assign the name `data-lake` to the role. Finalize the creation by clicking **Create Role**.
   
   ![Name the Role](/images/2.prerequisite/2.2.iamrole/06-iamrole.png)
   ![Create the Role](/images/2.prerequisite/2.2.iamrole/07-iamrole.png)

{{%notice note%}}
Note the name of your S3 bucket. You will need to use its name in future steps.
{{%/notice%}}

#### Upcoming Steps

With the IAM Role configured, we're now set to proceed with the data ingestion process, leveraging AWS Lambda to push data into our data lake.
