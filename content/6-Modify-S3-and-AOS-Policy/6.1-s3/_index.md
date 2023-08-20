---
title: "Modifying the S3 Bucket Policy for Lambda Access"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 6.1 </b> "
---

#### Modifying the S3 Bucket Policy for Lambda Access

In this section, we will modify the S3 bucket policy to allow the Lambda function to write data to the S3 bucket.

1. **Navigate to the Amazon S3 console.**
2. **Open the bucket that you created previously.**
3. Choose the **Permissions** tab, scroll to **Bucket policy**, and choose **Edit**.
   ![Bucket Policy](/images/6.modify/6.1.s3/01-s3.png)
4. Replace the existing policy with the following JSON code, ensuring you replace the placeholders `<LambdaRoleARN>` with the **ARN of your Lambda role** and `<BucketARN>` with the **ARN of your S3 bucket**:
    ```json
    {
      "Version": "2012-10-17",
      "Id": "ExamplePolicy",
      "Statement": [
        {
          "Sid": "ExampleStmt",
          "Effect": "Allow",
          "Principal": {
            "AWS": "<LambdaRoleARN>"
          },
          "Action": "s3:*",
          "Resource": "<BucketARN>/*"
        }
      ]
    }
5. In the **Bucket policy** editor, paste the bucket policy that you configured. Choose **Save changes.**
   
   ![Bucket Policy](/images/6.modify/6.1.s3/02-s3.png)


#### Conclusion

You have now modified the S3 bucket policy to allow the Lambda function to upload temperature files to your bucket.
