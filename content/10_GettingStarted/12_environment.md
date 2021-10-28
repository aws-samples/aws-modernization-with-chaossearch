+++
title = "Environment"
chapter = true
weight = 12
+++

The ChaoSearch platform separates compute from storage. While compute is provided by ChaosSearch on a true SaaS model (no instances to choose or manage), all the storage is provided by AWS S3.

The data is ingested directly, and indexed back to customer's AWS S3 buckets. Access to the data from the Chaossearch platform is controlled by the customer through standard IAM policies.

{{% notice info %}}
For this workshop, we will be using an S3 bucket that is already accessible and populated with ELB logs. 
{{% /notice %}}

Using Role Based Access Controls (RBAC), separated accounts are created for each user, and credentials provided prior to the workshop. 

{{% notice note %}}
For more information on AWS prerequisites check [ChaosSearch Quick Start Guide](https://docs.chaossearch.io/docs/quick-start-guide)
{{% /notice %}}
