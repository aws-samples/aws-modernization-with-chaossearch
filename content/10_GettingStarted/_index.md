---
title: "Getting Started"
chapter: true
weight: 10
---

## Introduction

ChaosSearch is a fully managed, secure service on AWS backed by Amazon S3 as a data store. With a few clicks, customers can be up and running in minutes, all at a fraction of the cost of running your own Elasticsearch cluster or ELK Stack.

Learn how ChaosSearch unlocks your Amazon S3 storage and turns it into a secure, durable, and cost-effective search platform with both Amazon S3 and Elasticsearch APIs.

### Step 1 - Discover and Index data directly from S3

The first step is to allow ChaosSearch to connect to your S3 buckets using standard IAM Role and Policy or the Cloudformation template. After discover and cataloging the contents of your S3 bucket(s), users can set customizable filters to create the *Object Groups* and index the data in virtual buckets for fine-grained analysis.

### Step 2 - Transform the data with Refinery

ChaosSearch *Views* are logical indexes based on the physical indexes (*Object Groups*). The *Refinery* allows users the unique ability to clean, prepare, and transform the index data. Schema Transformation can be applied to one or many fields to change data types (from string to numeral for example), expand the content of a single field into multiple fields for better analysis, among other capabilities. All the transformations can be done without the need to re-index data and you can have multiple *Views* based on the same *Object Group* for different analysis types or personas.

### Step 3 - Visualization and Alerting

Data from the *Views* are accessible through the Elasticsearch API and also using the built-in Kibana (based on the OpenDistro). Users can create individual visualizations or group multiple on a dashboard. There is also alerting capabilities to allow automated monitoring of events, and customizable triggers to send notifications when data crosses the thresholds set. ChaosSearch provides multiple alerting options with built-in integrations for Slack, Amazon Chime and custom Webhooks (integrates with your existing monitoring infrastructure or any third-party system.)