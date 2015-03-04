cato-tasks
==========

Example Tasks for ClearCode Automate

This repo contains sample Tasks that can be used as a tutorial for learning Automate Task development. 

Each directory has a README file which will walk you through the sample Task. 

To import a Task into your local Automate environment there are two options:

**Option A** 

Clone this repo locally and import the `.json` files found in the example directory.

    git clone git://github.com/cloudsidekick/cato-tasks.git

Then in Automate go to `Tasks`, `Import a Backup File`. 

Click the `Select` button and navigate to the example directory (such as cato-tasks/looping).

Select the `.json` file in the example directory (e.g. Example-Looping.json).

Click the `Load` button. 

Next click the `Import` button. 

**Option B** 

Import the task files individually directly from Github.

    On the Github website, drill into an example directory, such as looping. 
    
e.g.:

    https://github.com/cloudsidekick/cato-tasks/tree/master/looping

Click on the `.json` file found in the directory.  
    
e.g.:

    Example-Looping.json

On this page, click the `Raw` button right above the code. This will redirect you to the raw json file representing the task. 

    https://raw.github.com/cloudsidekick/cato-tasks/master/looping/Example-Looping.json

Copy the link out of your browser's address field. 

Then in Automate go to `Tasks`, `Import a Backup File`.  Paste the raw url to the file in the URL input box and press enter. The big box in the middle should populate with json. 

Next click the `Import` button. 

**Option C**

Go through the same process for Option B above except that except instead of copying the link to the raw file, copy all of the json to your browsers copy buffer (CNTL-A, CNTL-C) and paste it into the big box on the `Import a Backup File` page and click `Import`.  

**Final Thoughts**

Regardless of which option is used, you can now edit and run the task in your environment. Refer to the README file in each directory for the task walkthrough. 

Please send suggestions / questions to support@clearcodelabs.com
