---
title: "Adding Environment Variables to the Lambda Function"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 7 </b> "
---

#### Adding Environment Variables to the Lambda Function

In this section, we will add environment variables to the Lambda function to ensure it can interact with the OpenSearch Service domain.

1. **Navigate to the Lambda console.**
2. Select the **function** have been created (e.g., `upload-data`)
3. Choose the **Configuration** tab. On the tab menu, **choose Environment variables** and then **choose Edit**.
   ![Environment Variables](/images/7.adding-var-lambda/01-adding-var-lambda.png)
4. **Choose Add environment variable** and configure the following settings:
    - Key: `ES_DOMAIN_URL`
    - Value: Paste the OpenSearch Service domain endpoint that you noted previously. It should look similar to the following example:
      ```
      https://search-water-temp-domain-xxxxxxxxxxxxxxxxxxxxxxxxx.us-east-1.es.amazonaws.com
      ```

{{%notice warning%}}
Ensure that the OpenSearch Service domain endpoint doesn’t have a slash (/) at the end.
{{%/notice%}}


   ![Add Environment Variable](/images/7.adding-var-lambda/02-adding-var-lambda.png)
5. **Choose Save**.

#### Conclusion

You have successfully added an environment variable to the Lambda function, allowing it to interact with the OpenSearch Service domain.
