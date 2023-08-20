---
title : "Creating an S3 bucket"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

In this step, we will create an S3 bucket to store session logs sent from EC2 instances.

#### Create **S3 Bucket**

1. Access [S3 service management console](https://s3.console.aws.amazon.com/s3/home)
  + Click **Create bucket**.

![S3](/images/4.s3/01-s3.png)

2. At the **Create bucket** page.
  + In the **Bucket name** field, enter the bucket name (e.g., `datalakes-workshop1`)
  + In the **Region** section, select **Region** you are doing the current lab.

{{%notice note%}}
The bucket Region should be the same Region that your OpenSearch Service cluster is in.
{{%/notice%}}

 {{%notice info%}}
The name of the S3 bucket must not be the same as all other S3 buckets in the system. You can substitute your name and enter a random number when generating the S3 bucket name.
{{%/notice%}}

![S3](/images/4.s3/02-s3.png)

{{%notice note%}}
Note the name of your S3 bucket. You will need to use its name in future steps.
{{%/notice%}}

3. Scroll down and click **Create bucket**.

![S3](/images/4.s3/03-s3.png)

#### Conclusion
With the Amazon S3 bucket now set up, you have a dedicated space to store and manage the data for your data lake. In subsequent sections, we'll explore how to ingest data into this bucket and integrate it with other AWS services.