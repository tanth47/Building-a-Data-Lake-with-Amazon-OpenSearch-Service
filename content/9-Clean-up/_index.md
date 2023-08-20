---
title: "Clean Up Resources"
date: "`r Sys.Date()`"
weight: 9
chapter: false
pre: " <b> 9. </b> "
---

#### Delete IAM Roles and Policies

1. Navigate to the [IAM console](https://console.aws.amazon.com/iam/).
2. In the left navigation pane, choose **Roles**.
3. Find the role you've created for this workshop and delete it.
   ![Delete IAM Role and Policies](/images/9.clean-up/01-clean-up.png)

#### Delete the Amazon OpenSearch Service Domain

1. Navigate to the **OpenSearch Service console**
2. Choose the domain you've created.
3. Click on **Delete**.

   ![Delete OpenSearch Domain](/images/9.clean-up/02-clean-up.png)

#### Empty and Delete the S3 Bucket

1. Go to the [S3 console](https://console.aws.amazon.com/s3/).
2. Open the bucket you've created.
3. First, empty the bucket by selecting all the files and choosing **Delete**.
   ![Empty and Delete S3 Bucket](/images/9.clean-up/03-clean-up.png)
   ![Empty and Delete S3 Bucket](/images/9.clean-up/04-clean-up.png)
4. After ensuring the bucket is empty, delete the bucket itself.
   ![Empty and Delete S3 Bucket](/images/9.clean-up/05-clean-up.png)

#### Delete the Lambda Function

1. Navigate to the [Lambda console](https://console.aws.amazon.com/lambda/).
2. Choose the function you created.
3. Click on **Actions** and select **Delete function**.

   ![Delete Lambda Function](/images/9.clean-up/06-clean-up.png)

#### Delete the API Gateway

1. Go to the [API Gateway console](https://console.aws.amazon.com/apigateway).
2. Select the API you've set up.
3. From the **Actions** dropdown, choose **Delete API**.

   ![Delete API Gateway](/images/9.clean-up/07-clean-up.png)

#### Conclusion

You've successfully cleaned up all the resources you created during this workshop. It's always a good practice to delete unused resources to avoid incurring unnecessary costs.
