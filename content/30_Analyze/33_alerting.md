---
title: "Alerting"
chapter: true
weight: 33
---

## Alerting

ChaosSearch enables you to monitor your data and send alert notifications automatically to users. Based on open standard Kibana tooling, it is easy to set up, manage, and monitor your alerts.

This guide will walk through the creation of an alert, that includes 3 steps:

 - Create Monitor - Creating a monitor in ChaosSearch will allow you to specify a particular value that should be monitored when defining the monitor by utilizing the extraction query or visual graph.

 - Create Trigger - To create a trigger, you specify the threshold value for the field that is being monitored. If the value of the field exceeds the threshold, the Monitor enters the Active state.

 - Create Destination - Choose between a Slack channel, AWS Chime, or you can set up a custom webhook to receive messages. If you choose a custom webhook, you will set up headers and a message body, and the plugin will POST its message to the destination URL.

 In Kibana, Alerts are accessed by selecting *Alerting* on the left menu, as indicated on the pictured below:

![](/images/analytics/kibana_alerting.jpg)


### Alerting Exercise

For this exercise we will monitor ELB error logs using the *backend\_status\_codes* field (NOT 200). The alert will be sent to a Slack workspace that has already been defined.

Objectives:

 - Create *Monitor*
 - Create *Trigger* and *Action*

### Create Monitor

To start, select the *Dashobard* tab on the *Alerting* page. This page shows all existing monitors. In the picture below, we have no monitors defined.

![](/images/analytics/viewmonitors.jpg)

Click on **Create Monitor** in the middle of the screen. In the **Configure Monitor** screen enter the following:

- Monitor Name: Enter **chaosXX-mon**
- Monitor State: leave unchecked to enable the monitor after creation

On the *Define Monitor* section, enter the following:

- How do you want to define the monitor?: Select **Define using visual graph**
- Index: From the dropdown menu, select the *View* you created in the *Refinery* exercise **(chaosXX-obj)**  
- Timefield: From the dropdown menu, select **timestamp**

{{% notice info %}}
If you didn't create a *View* in the first Exercise you may use **chasoMSTR-v**.
{{% /notice %}}

At this point your screen should look like this:

![](/images/analytics/definemonitor.jpg)

Scroll down to view the remainder of the screen. The first thing you will see is the graph, this is a result from our choice for **How do you want to define the monitor:** **Define using visual graph.**.

Since we are looking for error status codes, we will define **Create Monitor for** using `backend_status_codes IS NOT 200`.

For the interval, we can keep the **FOR THE LAST** field as **15 days**

Click on the **Where** clause and type/select:

- Field: **backend\_status\_code**
- Operator: **is not**
- Value: **200**

  ![](/images/analytics/monitor_filter.jpg)

You can leave the **Monitor Schedule** section at the bottom of the screen unchanged. 

Select the **Create** button on the bottom right of the screen. This will create the **Monitor** and bring you to a **Create Trigger** screen for the monitor.

### Create Trigger and Action

To create the **Trigger** enter the following:

- Trigger name: **chaosXX-trg**
- Security Level: Severy level for the alert. Leave at **1**
- Trigger Condition: Number of occurrences to trigger the alert. Click on the dropdown and select **IS ABOVE** - **10**.

![](/images/analytics/definetrigger.jpg)

On the graph you can see both the count of filtered events (status code not 200) over time, as well as a red line showing the threshold for the trigger.

Now we need to define what to do when the *Alert* has triggered. On the **Configure actions** section, enter the following:

- Action Name: **chaosXX-act**
- Destination: From the dropdown menu, select **SlackDemo -(Slack)**
- Message Subject: **chaosXX Alert**

Scroll down and look at the **Message Preview**, then Select **Create** at the bottom right of the screen. You are brought to the screen for the alert you just created.

![](/images/analytics/alertdashboard.jpg)

Your alert is created and will generate notifications on Slack every minute based on the triggering conditions configured.

{{% notice note %}}
ChaosSearch Alerting documentation [https://docs.chaossearch.io/docs/alerting-overview](https://docs.chaossearch.io/docs/alerting-overview)
{{% /notice %}}


