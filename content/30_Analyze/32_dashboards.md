---
title: "Dashboards"
chapter: true
weight: 32
---

## Dashboards

Kibana dashboards are a collection of visualizations created from your ChaosSearch indices. Dashboards can give near real-time insight into the types of events being logged into your S3 bucket.

Let's take a look at one of the pre-polulated dashboards. Select **Dashboard** on the left side menu of the screen, then scroll the list and Select the **ELB Dashboard.**

![](/images/analytics/selectdashboard.jpg)

Kibana dashboards are dynamic, by clicking on any visualization the whole dashboard will be filtered according to the selection. For example, you can select **404** on the **AWS ELB - Backend status code** visualization to filter all the visualizations for this particular error code.

![](/images/analytics/elbdashboard.jpg)


{{% notice note %}}
ChaosSearch Analytics documentation [https://docs.chaossearch.io/docs/kibana](https://docs.chaossearch.io/docs/kibana)
{{% /notice %}}