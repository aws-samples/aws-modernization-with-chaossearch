+++
title = "Objective"
chapter = true
weight = 11
+++

In this workshop we will use ChaosSearch to discover and monitor 404 errors from Elastic Load Balancing (ELB) logs stored in S3. 
The workshop will guide you through hands-on exercises to:

- Discover ELB logs and create an *Object Group* and index using the *Storage* tab
- Create a *View* and transform the data in the *Refinery* tab
- Visualize the data in the *View* using the built-in *Kibana*
- Create an Alert Monitor based on thresholds using *Kibana* and Slack

Each participant will be provided a separate set of credentials to access the platform. We suggest following the naming convention when creating the resources on each section of the workshop:

- Object Group = **chaosXX-obj**
- View = **chaosXX-v**
- Monitor = **chaosXX-mon**
- Trigger = **chaosXX-trg**
- Action = **chaosXX-act**

(Please replace XX with your user ID provided)

Each section will be explained before the exercise and help is available by asking questions in the chat window.


{{% notice tip %}}
This workshop is design in a way that each section builds upon the last, but in case you don't complete a particular section you can always refer to the master objects listed below to continue the workshop.
{{% /notice %}}

- Object Group = **chaos-mstr-obj**
- View = **chaosMSTR-v**
- Monitor = **chaosMSTR-mon**
- Trigger = **chaosMSTR-trg**
- Action = **chaosMSTR-act**

{{% notice note %}}
ChaosSearch documentation can be found [here](https://docs.chaossearch.io/docs) 
{{% /notice %}}
