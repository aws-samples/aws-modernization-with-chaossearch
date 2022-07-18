---
title: "Chaos Refinery®"
chapter: true
weight: 22
---

## Refinery

The ChaosSearch Refinery® is a major component of the ChaosSearch service. It provides a variety of capabilities unique to the ChaosSearch platform and will provide a streamlined approach to transforming your data.

The Refinery offers a collection of tooling geared to cleaning, preparing, and transforming data such that users can programmatically and visually interact with information as needed. 

In this exercise we will create a *View* for the Object Group created. 

### Select the *Object Group*

Go to the **Refinery** tab and click **Create View** to start:

![](/images/indexandtransform/createview.jpg)

Select the *Object Group* you created on the previous step and click *Next*.

![](/images/indexandtransform/selectobjectgroup.jpg)

### Transform the data

You are now presented with the Schema Transformation page where you may change data types and perform transformations in the view. 

For this exercise we will be using the Schema Transformation capabilities to breakout the field *cs\_uri\_stem* into 3 different fields: domain, port and path. 

To start, either scroll down the fields list until you see the *cs\_uri\_stem* field or you can enter cs\_uri\_stem in the **Search Fields** box.

![](/images/indexandtransform/selectfield.jpg)

Then click on the gear icon on the right side of the screen to create the transformation.

First, select **Refresh** to get a preview of the current values for the field.
![](/images/indexandtransform/preview_content.jpg)

Then, select **Materialize with Regex** on the **Select Transform** dropdown. This options allows to use a regex pattern to capture values.

For **Field Transform Pattern (REGEX):** Enter `https:\\/\\/(\\S+):(\\d+)(\\S+)`. Then select the **+ Add Field** 3 times to add 3 new fields:

- Domain: data type: *STRING*
- Port: data type: *NUMBER*
- Path: data type: *STRING*

Then select **Refresh** to preview the data after the transformation.


Your screen should now look like:

![](/images/indexandtransform/createtransformation.jpg)

Now select **Save Transform** at the top right of the screen. Scroll through the fields and note the 3 fields you just added to validate the transformation. Then select **Next** at the bottom right of the screen to continue.

On the next screen, select the **timestamp** as the **Timestamp Field,**.

![](/images/indexandtransform/savetransform.jpg)

### Create the *View*

The last step is give a name to the *View* and select some options:  

- **Cacheable**: when enabled is used for caching the results of queries. After an initial query is executed, results are cached for improved search results and experience. 
- **Case Insensitive**: by selecting Case insensitive users will now be able to search against terms regardless of case.
- **Overwrite**:overwrite existing views.

For this exercise, we recommend leaving all options unchecked.

Finally, click on **Create** to create the *View*.

![](/images/indexandtransform/createviewfinal.jpg)