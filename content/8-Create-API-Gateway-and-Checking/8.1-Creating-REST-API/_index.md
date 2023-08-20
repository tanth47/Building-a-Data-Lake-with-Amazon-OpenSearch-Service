---
title: "Creating a API Gateway"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 8.1 </b> "
---

#### Setting Up the API Gateway

In this section, we will establish an API Gateway to facilitate data reception from the sensors. This API Gateway will trigger the Lambda function, which will subsequently store the data in Amazon S3 and OpenSearch Service.

1. **Access the API Gateway console**.
   ![API Gateway Console](/images/8.api-and-check/8.1.api/01-api-gateway.png)

2. On the **REST API** card, select **Build**.
   ![REST API Build Option](/images/8.api-and-check/8.1.api/02-api-gateway.png)

3. For **Create new API**, opt for **New API**. Name the API as `sensor-data` and then initiate **Create API**.
   ![API Creation](/images/8.api-and-check/8.1.api/03-api-gateway.png)

4. In the **Resources** section, from the **Actions** menu, choose **Create Method**. From the dropdown, select **POST**.
   ![POST Method Selection](/images/8.api-and-check/8.1.api/04-api-gateway.png)
   ![POST Method Selection](/images/8.api-and-check/8.1.api/05-api-gateway.png)


5. For **POST - Setup**, ensure:
   - **Integration type** is set to **Lambda Function**.
   - **Lambda Function** box contains `upload-data`.
   - Confirm by selecting **Save**.
   ![Lambda Function Configuration](/images/8.api-and-check/8.1.api/06-api-gateway.png)
   ![Save Configuration](/images/8.api-and-check/8.1.api/07-api-gateway.png)

#### Testing the API Gateway

1. In the **POST - Method Execution** section, opt for **TEST**.
   ![Method Execution Test](/images/8.api-and-check/8.1.api/08-api-gateway.png)

2. In the **Request Body** box, input the following JSON:
   ```json
   {
     "sensorID" : "0047",
     "temperature" : "23"
   }
   ```
   ![Request](/images/8.api-and-check/8.1.api/09-api-gateway.png)

#### Conclusion
Successfully, you've set up and tested an API Gateway to receive data from sensors and activate the Lambda function.