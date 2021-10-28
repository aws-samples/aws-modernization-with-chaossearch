---
title: "Analyze"
chapter: true
weight: 30
---

## Analytics

On the **Analytics** tab you can access the built-in Kibana interface, with a few extra features: a query progress bar at the top and a button to cancel the query. ChaosSearch built-in Kibana is based on the Open Distro open-source project.

At the top of your screen, in the ChaosSearch Tabs, select **Analytics**.

Objectives:

- Discover the data
- Create filters
- Create Visualizations
- Dashboards

### Discover the data

On the left side of the screen, select **Discover**.

On the drop-down list, select the **View** you just created (**chaosXX-v**) 

{{% notice info %}}
If you didn't create an a View in the previous exercise, you may use **chasoMSTR-obj**. 
{{% /notice %}}
 
![](/images/analytics/selectview.jpg)

Now Select **Last 30 Days** from the **Show Dates** drop-down time filter at the top-right side of the screen.

![](/images/analytics/timefilter.jpg)

The screen will show an histogram of the top 500 logs for the last 30 days on the top, and a pannel below with details on each log event. Click on the arrow on the left side of each log to check all the fields and values of the log.

### Create filters

Now we want to filter out the "good requests" (Status Code: 200) to view only the error codes.

To do this select **+ Add Filter** on the top left of the screen:

- Field: **backend\_status\_code** 
- Operator: **is not**
- Value: **200**

Click **Save**.

![](/images/analytics/create_filter.jpg)

Now both the histogram and the log details pannel are filtered for Status Codes different than 200.