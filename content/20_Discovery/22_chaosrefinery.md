---
title: "Chaos Refinery®"
chapter: true
weight: 22
---

## Refinery

The ChaosSearch Refinery® is a major component of the ChaosSearch service. It provides a variety of capabilities unique to the ChaosSearch platform and will provide a streamlined approach to transforming your data.

The Refinery offers a collection of tooling geared to cleaning, preparing, and transforming data such that users can programmatically and visually interact with information as needed. 

### Refinery Exercise

In this exercise we will create a *View* for the Object Group (**chaosXX-obj**) already created. 

{{% notice info %}}
If you didn't create an Object Group in the first exercise you may use the master object: **chas-mstr-obj**. Our view name will be **chaosXX-v** where XX is the ID provided in the workshop package.
{{% /notice %}}

Objectives:

- Select the *Object Group* 
- Transform the data
- Create the *View*

### Select the *Object Group*

Go to the **Refinery** tab and click **Create View** to start:

![](/images/preparing/createview.jpg)

Use the search box to find and select the *Object Group* created on the previous step **(chaosXX-obj)**:

![](/images/preparing/selectobjectgroup.jpg)

The **Index Window** option can be used to select a specific time window for the *View*. For this exercise we will setting the *View* for the entire index so we can leave the box unchecked.

Select **Next** at the bottom right side of the screen to proceed.

### Transform the data

You are now presented with the Schema Transformation page where you may change data types and perform transformations in the view. 

For this exercise we will be using the Schema Transformation capabilities to breakout the field *cs\_uri\_stem* into 3 different fields: domain, port and path. 

To start, either scroll down the fields list until you see the *cs\_uri\_stem* field or you can enter cs\_uri\_stem in the **Search Fields** box.

![](/images/preparing/selectfield.jpg)

Then click on the gear icon on the right side of the screen to create the transformation.

First, select **Refresh** to get a preview of the current values for the field.

Then, select **Materialize with Regex** on the **Select Transform** dropdown. This options allows to use a regex pattern to capture values.

For **Field Transform Pattern (REGEX):** Enter `https:\\/\\/(\\S+):(\\d+)(\\S+)`. Then select the **+ Add Field** 3 times to add 3 new fields:

- Domain: data type: *STRING*
- Port: data type: *NUMBER*
- Path: data type: *STRING*

Then select **Refresh** to preview the data after the transformation.


Your screen should now look like:

![](/images/preparing/createtransformation.jpg)

Now select **Save Transform** at the top right of the screen. Scroll through the fields and note the 3 fields you just added to validate the transformation. Then select **Next** at the bottom right of the screen to continue.

On the next screen, select the **timestamp** as the **Timestamp Field,**.

![](/images/preparing/savetransform.jpg)

### Create the *View*

The last step is give a name to the *View* **(chaosXX-v)** and select some options:  

- **Cacheable**: when enabled is used for caching the results of queries. After an initial query is executed, results are cached for improved search results and experience. 
- **Case Insensitive**: by selecting Case insensitive users will now be able to search against terms regardless of case.
- **Overwrite**:overwrite existing views.

For this exercise, we recommend leaving all options unchecked.

Finally, click on **Create** to create the *View*.

![](/images/preparing/createviewfinal.jpg)





{{% notice note %}}
ChaosSearch Refinery documentation [https://docs.chaossearch.io/docs/refinery](https://docs.chaossearch.io/docs/refinery)
{{% /notice %}}