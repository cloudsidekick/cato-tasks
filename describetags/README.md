DescribeTags
=============

This example task demonstrates using the AWS DescribeTags command and parsing the results. This example demonstrates using xpath to parse the results returned from AWS and looping through the results. 

Requirements: you will need to setup a Cloud Account with the proper AWS credentials.

Also, you should probably take at look at Example Task ex-001 first. 

When you run the sample, make sure to use Verbose logging so that you can see whats being returned from AWS. 

Walkthrough
-----------

Some of the steps in this task are the command type of "Comment". These commands will not be processed by the task engine an dare for documentation purposes only. 
We'll skip over them in this description as well. 

The **first DescribeTags step** performs the AWS DescribeTags command without any filters. It will return all objects with resource tags. 

Change the AWS Region to a region where your resources are. 

The **next step** is a Loop command. The counter variable is the variable that holds the loop iteration number. 

We will loop through the results returned from AWS, the xpath function "count" return the number of times the path //item/resourceId appears in the xml. We'll spin through the loop that many times. z is the counter variable. 
See http://www.w3schools.com/xpath/ for more on xpath queries.

In the "Action" section of the Loop command, the Log command is used. Again an xpath query is used and the counter variable is used for the index in the query.

Next we have the **Set Variables** command. In this step the key and value pair of the first resource returned from AWS are extracted and placed into the Cato variables named key and value. Variable names can be just about anything. 

In the **last step**, the If command is used to test to see if key is populated. The only way it wouldn't be is if your AWS region doesn't have any tags defined. 

If the key variable is populated, the action DescribeTags will be executed with the filters key and value used. When this is run, it should return xml containing only one resource. 
