Digital Ocean Sample Task
=============

This task is intended to show the user how to use the Digital Ocean task commands. Specifically this task will lookup an ssh key id, boot a droplet server, interact with it, use the various stop and start command and destroy the server. There is also a generic command that can be used to interact with the non-droplet api commands.

Requirements: 

* Cloud Account setup in Cato with valid Digital Ocean credentials (see below)
* Cloud Endpoint setup in Cato (see below)
* Become a little familiar with the Digital Ocean API: https://developers.digitalocean.com

Set Up the Digital Ocean Service Endpoint
-----------

First define the Web Service Endpoint within Cato. In the Cato administration console, navigate to Configuration -> Manage Clouds. If the Digital Ocean web service endpoint is not already defined (Cloud Name = digital-ocean), click on the Import button. This will create the Digital Ocean endpoint as well as any other public cloud provider in the Cato configuration files (such as AWS). 

Digital Ocean Cloud Account Credentials
-----------

To enable Cato to communicate with the Digital Ocean Web Service, you will need to define the Client Id and API Key in Cato.

In Cato navigate to Configuration -> Manage Cloud Accounts. 

Click the Create button and select Digital Ocean in the Provider drop down. Fill in the following fields: Account Name, Client ID, API Key, API Key Confirm. Account Name is an arbitrary name for the set of credentials which will distinguish it from other credentials defined. Client ID and API Key can be found in the Digital Ocean console application. 

Select "digital-ocean" previously created as the Default Cloud. If you will be primarily using this cloud account for your Cato work, check the "Make Default" box. Click Save.

Finalize Digital Ocean Cloud Endpoint
-----------

Return to the Cloud Endpoint management page via Configuration -> Manage Clouds. Click on the digital-ocean clound endpoint row. In the Default Account list box, select the cloud account created in the previous step. Click Save.

Digital Ocean Ssh Keys
-----------

In order to ssh into linux virtual machines in Digital Ocean, Cato will need to know about the Ssh Keys defined in Digital Ocean. Assuming that you have already uploaded a public key and named it in Digital Ocean, this step will show you how to upload the private key portion into Cato.

Navigate to Security -> Manage Shared Credentials. Click Create. In the Name box on the left, enter the Ssh Key name defined in Digital Ocean. Click the Private Key tab on the right. Paste in the full private key text, including the following lines:

-----BEGIN RSA PRIVATE KEY-----
dkjfkjkldklgjdflk …
…
…
-----END RSA PRIVATE KEY-----

Click Save. You are now ready to create a task to interact with the Digital Ocean API. 


Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

When the task is run, it will prompt for an Ssh Key name that you have defined in Digital Ocean.

Run the task and notice the output in the log. 

