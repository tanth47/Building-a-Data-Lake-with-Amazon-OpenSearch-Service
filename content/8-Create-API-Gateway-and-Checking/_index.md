---
title: "Creating a REST API and Checking Solution"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 8. </b> "
---

#### Introduction

In this section, we will focus on setting up an API Gateway to receive data from the sensors and subsequently test the entire solution. The API Gateway will be responsible for invoking our Lambda function, which will process the data and store it in our Amazon S3 bucket and OpenSearch Service.

The first part will guide you through the process of creating the API Gateway, while the second part will ensure that our solution works as expected by testing the data ingestion and retrieval processes.

Let's get started!

#### Content

1. [Create a REST API](8.1-creating-rest-api/)
2. [Test the Solution](8.2-checking-solution/)