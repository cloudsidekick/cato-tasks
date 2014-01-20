Boot Ec2 and Install Tomcat
=============

This task will boot an ec2 server, ssh to the server, install Tomcat, perform a smoke test and terminate the ec2 server

Requirements: 

* Cloud Account setup in Cato with valid AWS credentials
* Cloud Endpoint setup in Cato with proper key pair name
* An Ubuntu image identified
* Security Group with ports 22, 8080 open and accessible

Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

When the task is run, it will prompt for the security group, image, instance type, ssh user and key pair name to use. 

The Command Line step assumes Ubuntu, this can be easily changed for other linux flavors.
