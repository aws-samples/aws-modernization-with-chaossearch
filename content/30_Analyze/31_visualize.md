---
title: "Visualize"
chapter: true
weight: 31
---

## Visualize

Visualize will provide different types of visualizations/graphs to analyze the data. You can select several chart types (bar, area, pie, heatmaps), counter, gauges, geolocation maps, among several other options. 

### Create Visualizations

One simple way to create visualizations is directly from the **Discovery** page. Just select any non-number field from the list of **Available Fields** on the left side of the screen to see a quick list of the top 5 values of the field.
You can for example search and select the **backend_status_code** field:

![](/images/analytics/quick_visualize.jpg)

Then click on **Visualize** button to create a visualization for this field. Kibana creates a quick bar chart based on the field **backend\_status\_code**:

![](/images/analytics/quickvisualization.jpg)

Now you can explore the pre-populated visualizations available by clicking on **Visualize** on the left menu and selecting one of the visualizations from the list. 

Let's look for example at the pie chart for ELB Status Codes. Scroll down the list and select  **AWS ELB - Backend status codes**. 

![](/images/analytics/openvisualization.jpg)

Confirm the time filter (top-righ of the screen) is set to **Last 30 days** and the filter (top-left) is set to **NOT backend\_status\_code:200**

![](/images/analytics/filtervisualization.jpg)