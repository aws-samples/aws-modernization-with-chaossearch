+++
title = "Connect ChaosSearch"
chapter = true
weight = 15
+++

After your first login into ChaosSearch, you will be requested to create an IAM Role with the appropriate permission to allow ChaosSearch to access the S3 buckets.

Please follow the instructions below:

1. Click on the *Open Cloudformation* button.
![](/images/gettingstarted/create_cloudformation.jpg)

2. You will be redirected to the AWS CloudFormation Console, at the *Create stack* page.
![](/images/gettingstarted/create_stack.jpg)

3. Scroll-down to the end of the page (keep all the defaults), check the acknowledgment box, and click *Create stack*
![](/images/gettingstarted/create_stack_final.jpg)

4. When stack creating is completed, click on the *Output* tab and copy the Role ARN as demonstrated below:
![](/images/gettingstarted/stack_completed.jpg)
 
![](/images/gettingstarted/stack_output.jpg)

5. Go back to the ChaosSearch console, paste the Role ARN, and click *Next*.
![](/images/gettingstarted/role_arn.jpg)

6. Click the *Back* button at the top-left to go back to the *Storage* tab. 
![](/images/gettingstarted/cs_storage.jpg)

You should see you S3 bucket listed. Click on the bucket name to list the objects inside the bucket.

![](/images/gettingstarted/cs_bucket_list.jpg)


