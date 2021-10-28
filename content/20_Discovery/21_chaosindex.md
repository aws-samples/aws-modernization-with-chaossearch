---
title: "Chaos Index®"
chapter: true
weight: 21
---

## Chaos Index®

The ChaosSearch platform is backed by a new and powerful indexing technology, Chaos Index®, an index file format that provides both relational queries and text search in one representation. This format significantly compresses data compared to existing index technologies. Chaos Index® is uniquely designed to exploit the cost efficiency of object storage such as Amazon S3, while still providing high performance and elastic scale capabilities.

### Start Indexing

Your screen should now look like the following, you can begin indexing by clicking **Start Indexing**: 

![](/images/preparing/indexing.jpg)

When the indexing has completed your screen should look like the following:

![](/images/preparing/indexingdone.jpg)

{{% notice info %}}
ChaosSearch dinamically builds the mappings for the index structure, so any new fields captured in the log files are automatically added to the index, with the appropriate data type assigned.
{{% /notice %}}

{{% notice note %}}
Chaos Index® documentation [https://docs.chaossearch.io/docs/creating-object-groups](https://docs.chaossearch.io/docs/creating-object-groups)
{{% /notice %}}