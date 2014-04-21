cato-tasks
==========

Example Tasks for Cloud Sidekick Cato. 

This repo contains sample Tasks that can be used as a tutorial for learning Cato Task development. 

Each directory has a README file which will walk you through the sample Task. 

To import a Task into your local Cato environment there are two options:

**Option A** 

Clone this repo locally and import the `.csk` files found in the example directory.

    git clone git://github.com/cloudsidekick/cato-tasks.git

Then in Cato go to Configuration, Import a Backup File. 

Click the `Select` button and navigate to the example directory (such as cato-tasks/looping).

Select the `.csk` file in the example directory (e.g. Example-Looping.csk).

Click the `Load` button. 

Next click the `Import` button. 

**Option B** 

Import the .csk files individually directly from Github.

    On the Github website, drill into an example directory, such as looping. 
    
e.g.:

    https://github.com/cloudsidekick/cato-tasks/tree/master/looping

Click on the `.csk` file found in the directory.  
    
e.g.:

    https://github.com/cloudsidekick/cato-tasks/blob/master/looping/Example-Looping.csk

On this page, click the `Raw` button. This will redirect you to the raw xml file representing the task. 

    https://raw.github.com/cloudsidekick/cato-tasks/master/looping/Example-Looping.csk

Copy the link out of your browser's address field. 

Then in Cato go to `Tasks -> Import a Backup File`.  Paste the raw url to the file in the URL input box and press enter. The big box in the middle should populate with xml. 

Next click the `Import` button. 


Regardless of which option is used, you can now edit and run the task in your environment. Refer to the README file in each directory for the task walkthrough. 

Please send suggestions to support@cloudsidekick.com
