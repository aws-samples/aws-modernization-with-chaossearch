---
title: "Discovery"
chapter: true
weight: 20
---

## Storage

The Storage section of the **ChaosSearch** platform is the entry point to ChaosSearch. From here, you will be able to start solving some of the more common challenges cloud users face around log analytics at scale. 

The S3 buckets will be listed on the left hand side of the page. The **chaosdemo-datasets** bucket is pre-populated with several log samples, including the ELB logs that we will be using for this workshop.

![](/images/storage/storage.jpg)


### Bucket Discovery

Use the Data Discovery feature to quickly catalog and report on a variety of data sources in your buckets.

Select **chaosdemo-datasets** and highlight the **Bucket Content**. The Discovery process should start automatically, if not just select **Discover Bucket** to start the discovery.

![](/images/storage/bucketdiscovery.jpg)

### Storage Exercise

For this exercise we will group ELB Logs together in a virtual bucket called *Object Group*. We will apply a filter to select only the ELB logs, and then proceed to create an index.

Objectives:

- Filter the ELB logs
- Format, preview and validate
- Create *Object Group*

### Filter ELB logs

To get started with object groups click on **Create Object Group** at the top of the screen:

![](/images/storage/createobjectgroup.jpg)

It is very common to have a single S3 bucket to store logs from multiple sources. In this case, the **chaosdemo-dataset** bucket available also contains multiple datasets. In order to filter on just the ELB Logs that we are interested for this exercice, let's do the following:

1. Select the **chaosdemo-datasets** bucket from the left hand menu

2. Filters can be applied using a **Prefix** or a **Regex Filter**. For this exercise will use the **Prefix**

    Prefix: **elb**

![](/images/storage/filteringdata.jpg)

The *Object Group Preview* shows all the files included on the **elb** prefix. Review and click **Next** to proceed.

{{% notice note %}}
There are many other options to filter and select data when creating the *Object Group*. Please check the [documentation](https://docs.chaossearch.io/docs/creating-object-groups) for more information.
{{% /notice %}}

### Format, preview and validate

The system automatically identifies the file format and compression. ChaosSearch can currently index LOG, JSON, and CSV formats, compressed or not. For the LOG files, ChaosSearch can also automatically indentify the different fields, and suggest a regex pattern to capture each one of them. It's possible to change or edit the suggested regex by clicking on the pencil icon.

For our exercise ChaosSearch recognizes the format as **LOG** with no **Compression**. Additionally a regex is suggested to capture and format the content. Click **Validate** to show the formatted data using the suggested regex.

![](/images/storage/formatandpreview.jpg)

You should now see a formatted preview of the data. Now select **Create Object Group** in the lower right hand side of the screen to proceed.

![](/images/storage/validateandcreate.jpg)


### Create *Object Group*

ChaosSearch can index data in different ways. *Static indexing* is used to index existing data in the bucket. *Live indexing* automates the index process using leveraging Amazon Simple Queue Service (SQS) to notify ChaosSearch when a new file lands in the S3, so ChaosSearch can collect the file and index automatically. There is also the option of *Realtime indexing* which also uses SQS but indexes in near realtime. Since we will be indexing historical/existing data, *Static indexing* is the best option.

On the **Create Object Group** box, enter the following information:

- **Name:** type the name for the Object Group (**chaosXX-obj** where the **XX** is your user ID provided)
- **Live Indexing** leave unchecked (Static indexing)
- **Indexing Interval:** leave unchecked. 
- **Retention:** uncheck the box for unlimited retention, or (optionally) set the retention period for the index.

After validating the selections, press **Create** to create the *Object Group*:

![](/images/preparing/objectgroupname.jpg)




