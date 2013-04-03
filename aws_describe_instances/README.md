List All EC2 Instances in All Regions
=============

This example will retrieve a list of AWS regions and get a list of EC2 instances and their status in each region. 

This task sample is meant to show the use of cross-region AWS automation, looping, codeblocks and xpath parsing.

Requirements: you will need to setup a Cloud Account with the proper AWS credentials.

When you run the sample, make sure to use Verbose logging so that you can see whats being returned from AWS. 

Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

The **first DescribeRegions step** performs the AWS DescribeRegions command. It will return a list of all of the AWS regions that we will use to spin through. Amazon returns XML from the api endpoint, we are storing it in the Result Variable "regions". 

The **next step** is a Loop command. The counter variable is the variable that holds the loop iteration number. 

We will loop through the results returned from AWS, the xpath function "count" return the number of times the path //regionInfo/item appears in the xml. We'll spin through the loop that many times. z is the counter variable. 
See http://www.w3schools.com/xpath/ for more on xpath queries.

Inside the loop the task has a Codeblock step. A codeblock is sort of a procedure that can be reused within this task. All variables in a task are global in scope so whatever variables are set before, during and after the codeblock will be accessible. In this case the "process_region" codeblock will be called.

To view the codeblock steps, scroll up to the top of the page and hover over the icon next to "MAIN". This will drop down the list of codeblocks available in this task. Select "process_region" and the view will change. 

In this codeblock the steps will query each region and generate a list of EC2 instances in each region. For specifics on each step, click on the "Notes" icon on the bottom of each step. Notes are user definable comments that can be used to document a task. For the rest of this example, refer to the "Notes". 
