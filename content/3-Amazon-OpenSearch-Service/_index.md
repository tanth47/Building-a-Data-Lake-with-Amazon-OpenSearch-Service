---
title : "Creating an Amazon OpenSearch Service cluster"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Introduction

Amazon OpenSearch Service makes it easy to deploy, operate, and scale OpenSearch for log analytics, application monitoring, full-text search, and more. In this guide, we'll walk through the steps to set up an Amazon OpenSearch Service domain.

#### Step-by-Step Guide to Create an Amazon OpenSearch Service Domain

1. **Access the Amazon OpenSearch Service Console**: Navigate to the Amazon OpenSearch Service

 ![Access the Service](/images/3.aos/01-aos.png)

2. **Initiate Domain Creation**: Click on **Create a new domain**.

  ![Create new Domain](/images/3.aos/02-aos.png)

3. **Configure Domain**: 
   - **Domain name**: `water-temp`
   - **Domain creation method**: Standard create
   - **Template**: Dev/test
   - **Deploy Option(s)**: Domain without standby
  ![Configure new Domain](/images/3.aos/03-aos.png)
   - **Engine Version**: 2.7(latest)
   - **Data nodes, Instance type**: t3.small.search
   - **Data nodes, EBS size per node**: 10GB
   - **Network**: Public access
  ![Configure new Domain](/images/3.aos/04-aos.png)
   - **Enable fine-grained access control**: Clear this setting
  ![Configure new Domain](/images/3.aos/05-aos.png)
   - **Access policy**: Configure domain level access policy, IPv4 address, Replace `*` by your IPV4, Action: Allow

{{%notice tip%}}
Find your IPv4 address by using an online lookup service (such as [What Is My IP](https://www.whatismyip.com/)) and note your IPv4 address.
{{%/notice%}}

  ![Configure new Domain](/images/3.aos/06-aos.png)

4. **Review and Create**: Go through the configurations and ensure everything is set up as per your requirements. Click on **Create**.
  ![Configure new Domain](/images/3.aos/07-aos.png?width=50)

{{%notice note%}}
The domain-creation process can take up to 15 minutes to complete. Just go aheead and comeback later.
{{%/notice%}}

#### Conclusion

With the Amazon OpenSearch Service domain now set up, you're ready to ingest and analyze data. In the upcoming sections, we'll dive deeper into integrating this with our data lake.

