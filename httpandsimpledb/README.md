HttpAndSimpleDB
=============

Creates a SimpleDB domain and adds items with attributes then loops through one of the items and prints to the log. Deletes the domain at the end. Shows how to use Xpath to loop through the results of an AWS query. Shows the http command to pull data.

Requirements: you will need to setup a Cloud Account with the proper AWS credentials.

Also, you should probably take at look at Example Looping and DescribeTags first.

When you run the sample, make sure to use Verbose logging so that you can see whats being returned from AWS. Then rerun it with a lower logging setting to see what it looks like with less output.

Walkthrough
-----------

Some of the steps in this task are the command type of "Comment". These commands will not be processed by the task engine an dare for documentation purposes only. 
We'll skip over them in this description as well. 

The **first Set Variable** command sets up the domain name. It will be a unique name for example purposes, using the special variable **_UUID** to genernate a unique identifier. 

The **CreateDomain** command create a SimpleDB domain, a cross between a RDMS database and table.

Change the AWS Region to a region where your resources are.

The **Http** command is used to put some external csv data and process the data into Cato variables. You can click on the Manage Variable button to see how variables are set up. 

The **first Loop** command is used to spin through the variable arrays and put the data into the new domain. 

The **SimpleDB Select** command is used to select all rows for General Motors. The previous **Set Variable** command defined the sql used.

The **DeleteDomain** command is used to get rid of the domain. Since this is an example, we're done with it. 

The **second Loop** command is used to spin through results of the select. Inside the loop we will add up all the amounts that GM took as part of the Tarp program.

The total number of results from the select are determined with:

    [[gm.count(//Item/Attribute)]]

The **Set Variable** command in the loop sets the total variable using the following:

    csk_calc([[total]] + [[gm.//Item[ [[z]] ]/Attribute/Value]])

The **csk_calc** function tells the Task Engine to perform math. The xpath query "gm.//Item[ [[z]] ]/Attribute/Value" will get the amount values out of the xml.

**Log Message** is used to display the total amount calculated. 
