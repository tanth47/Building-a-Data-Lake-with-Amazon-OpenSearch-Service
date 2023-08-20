---
title: "Modify OpenSearch Service Cluster for Lambda Access"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 6.2 </b> "
---

To ensure our Lambda function can access the OpenSearch Service cluster, we need to modify the cluster's access policy.

1. **Navigate to the OpenSearch Service console**.
2. **Select the appropriate domain** (e.g., `water-temp`). Ensure the **Domain status** says “Active.” If not, wait a few minutes and refresh the page.
3. Note the **Domain endpoint** for future section, which should look similar to the following example:
```https://search-water-temp-domain-xxxxxxxxxxxxxxxxxxxxxxxxx.us-east-1.es.amazonaws.com```

   ![Domain Status](/images/6.modify/6.2.opensearch/01-opensearch.png)

4. Choose **Actions** and select **Edit security configuration**.

   ![Edit security configuration](/images/6.modify/6.2.opensearch/02-opensearch.png)


5. Scroll to **Access policy** and review the policy. Currently, the policy restricts access by IP address. The current policy should look similar to the following example:

```json
{
    "Version": "2012-10-17",
    "Statement": [
    {
        "Effect": "Allow",
        "Principal": {
        "AWS": "*"
        },
        "Action": "es:*",
        "Resource": "arn:aws:es:us-east-1:000000000000:domain/water-temp/*",
        "Condition": {
        "IpAddress": {
            "aws:SourceIp": "x.x.x.x"
        }
        }
    }
    ]
}
```

6. Add **Lambda** access to the policy. The policy must look similar to the following example, but *with your account number and IP address*:

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
        "Effect": "Allow",
        "Principal": {
            "AWS": "*"
        },
        "Action": "es:*",
        "Resource": "arn:aws:es:us-east-1:000000000000:domain/water-temp/*",
        "Condition": {
            "IpAddress": {
            "aws:SourceIp": "x.x.x.x"
            }
        }
        },
        {
        "Effect": "Allow",
        "Principal": {
            "AWS": "arn:aws:iam::615700818209:role/data-lake"
        },
        "Action": "es:*",
        "Resource": "arn:aws:es:us-east-1:000000000000:domain/water-temp/*"
        }
    ]
}
```

7. **Review**.

   ![Review](/images/6.modify/6.2.opensearch/03-opensearch.png?width=50)

8. Choose **Save changes**

#### Conclusion

You have now modified the OpenSearch Service cluster to allow the Lambda function to access it.
