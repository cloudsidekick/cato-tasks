Example - Generating a Unique Name
=============

This example will show you how to generate a unique string that can be used as part of a name, such as for a virtual server or database.

It also will illustrate the use of the task command "substring".

Importing the Task
------------------

Import the task into Automate using the Task, Import a Backup File menu choice. Paste the following link into the "Enter a URL:" box, then click "Load", then "Import". 

Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

The **first two steps** show how to generate an UUID inside of a task. We are simply printing the two strings to the log. When you run the task you will first notice that both UUIDs generated are different. For more information on UUIDs and how they are generated to be unique, see the Wikipedia link below. 

The [$ $] syntax denotes a wrapped variable. The \_UUID and \_UUID2 variable names are ClearCode reserved names which will replace within the variable brackets a generated uuids either with dashes (the first) or without (the second). 

The **third step**  shows how to use the _Substring_ command. Any string in the Test box will be substituted for variables and a substring will be created using the Start and End positions. The value will be stored in a variable named in the Variable box. i

NOTE: It is important to note that the beginning position in this command in "1", not "0" as is in many programming languages.  

The **fourth and fifth steps** use the value generated in the third step to combine with a static name part to create a unique server or database name. The last step prints this new name to the log. 

Running
-------

Running this task requires no special setup or input.

UUIDs
-----

Read more about UUIDs here: http://en.wikipedia.org/wiki/Universally_unique_identifier

Typically for naming unique assets (servers, databases, etc.) the first 8 characters will be "unique enough". 
