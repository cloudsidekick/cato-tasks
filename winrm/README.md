Example - Winrm
=============

This example will show you how to use Windows Remote Management to interact with a MSFT Windows server. 

It also will illustrate the use of the features:

* Task Parameters
* Connecting to Windows using WinRM
* Powershell
* Setting variables from WinRM session
* Looping through variables
* WinRM error handling
* Various Windows management commands

Prerequisites
-------------

You must first have a Windows server available with WinRM setup and accessible to a local user account. See the following link for details on setting up WinRM.

http://docs.clearcodelabs.com/docs/automate/tasks/windows.html

Importing the Task
------------------

Import the example task into Automate using the Task, Import a Backup File menu choice. Paste the following link into the "Enter a URL:" box, then click "Load", then "Import". 

https://raw.githubusercontent.com/cloudsidekick/cato-tasks/master/winrm/Example-Winrm.json

Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

Step one establishes the winrm connection to the target server using the address and credentials passed in as parameters. 

Step two sets some variables. The second variable `target_dir` will be used to write a file temporarily. You can change the directory if you would like.

Step three is an example of the Powershell command. This script writes the file to the target directory using the Powershell StreamWriter method. This is also an example of using a Powershell "Here Document" for setting a variable with multiple lines, quotes and other special characters. Google "Powershell Here Document" for more info. 

Step four is a winrm command to the Windows command line shell (as opposed to Powershell). Click on the Options button. This reveals some of the Winrm command options. The one to take note of here is the `Return Code`. Windows command shell returns a 0 on success, 1 on fail.  Step five prints this return code to the log. 
 
Steps six  and seven are also examples of command line commands. Step eight is an example of a Task Comment. This step is for display purposes in the Task Editor only, not executed.

Step nine sets a variable called `_IGNORE_WINRM_ERRORS`. By default if a winrm command fails or errors, the task will stop executing. If this is flipped to TRUE, any errors will be ignored. For the first run of the task, keep this to FALSE. Step ten is simply a log message reiterating this.

Step eleven looks for the file again. However this file was deleted in step seven. If `_IGNORE_WINRM_ERRORS` is set to FALSE, the task will error. If it is set to TRUE, the task will continue. Step twelve prints the return code from step eleven. 

Step thirteen is an example of using `wmic` command in Windows. Google "Windows Management Instrumentation Command-line". Simply another way get information from Windows from the command line. The important thing about this step is variable population. Click on the Variables button. Notice the `load` variable is getting set positionally. Click on `Manage Variables` to see how it is configured. Variables are set in this way by parsing the output returned by a winrm command. See the following link for more details. 

http://docs.clearcodelabs.com/docs/automate/tasks/task-variables.html

Step fourteen print the load percentage determined from step thirteen. 

Step fifteen performs the Windows `set` command which prints the evironment variables out to stdout. Click on the Variables button here. Here we are setting an array of variables named VARNAME and VALUE, breaking up the lines by linefeed and columns by the equal sign. For however many rows there are, an array of each variable name will get set to that length. 

Step sixteen uses the arrays to print each array value independently. The `loop` command is similar to for loops in most programming languages. See the sections on the following page concerning `Arrays` for more information on referencing array variables. 

http://docs.clearcodelabs.com/docs/automate/tasks/task-variables.html

Finally step seventeen is another Powershell example. 

Running
-------

Running this task requires the input parameters for the address, username and password of the target Windows server. 

The first time you run the task, level the setting on step nine to FALSE. Once you are able to run the task to that point (no connectivity errors), then flip that step to TRUE and run again. 
