---
title: "Index and Transform"
chapter: true
weight: 20
---

## Discovery

The Storage section of the **ChaosSearch** platform is the entry point to ChaosSearch. From here, you will be able to start solving some of the more common challenges cloud users face around log analytics at scale. 
The S3 buckets will be listed on the left-hand side of the page. 
![](/images/indexandtransform/storage.jpg)

For this exercise we will group ELB Logs together in a virtual bucket called *Object Group*. We will apply a filter to select only the ELB logs, and then proceed to create an index.

### Filter ELB logs

To get started with object groups click on **Create Object Group** at the top of the screen:

![](/images/indexandtransform/createobjectgroup.jpg)

It is very common to store logs from multiple sources in a single S3 bucket. ChaosSearch support filtering based on the prefix, or regular expressions for more granular filtering.
For this workshop, the ELB log files are stored using the *elb-logs* prefix. So let's use that prefix:

1. Select the workshop bucket from the menu on the left and type *elb-logs* as the prefix.

![](/images/indexandtransform/filteringdata.jpg)

The *Object Group Preview* shows all the files included on the **elb-logs** prefix. Review and click **Next** to proceed.

### Format, preview and validate

ChaosSearch can currently index LOG, JSON, and CSV formats, compressed or not.

The ELB logs used on this workshop are recognized as **LOG** with no **Compression**, ChaosSearch then suggests a regex format the content.
You can click **Validate** to see a preview of formatted data using the suggested regex.

![](/images/indexandtransform/formatandpreview.jpg)

It's possible customize the regex, for example to change capture groups or names. To open the Regex Editor, click on the pencil icon as demonstrated below.

![](/images/indexandtransform/regex_editor_click.jpg)

![](/images/indexandtransform/regex_editor.jpg)

When done, click the **Create Object Group** in the lower right-hand corner of the screen to proceed.

### Create *Object Group*

ChaosSearch can index data in different ways. For this workshop we will use **Static indexing** which indexes data already stored in the bucket.

For production environments, the most common method is **Live indexing**, which automates the indexing process by leveraging [Amazon S3 Event Notifications](https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html) in association with [Amazon Simple Queue Service (SQS)](https://aws.amazon.com/sqs/) to notify ChaosSearch when a new object (log file) in created in the S3 bucket, and can then automatically collect and index the data. 

To complete the creation of the **Object Group**, type a name in the box and hit **Create**.

> **Info:** ChaosSearch supports unlimited retention, but optionally a Retention Policy can be defined to automate the retention of the indexes.
 
After validating the selections, press **Create** to create the *Object Group*:

![](/images/indexandtransform/og_name.jpg)




