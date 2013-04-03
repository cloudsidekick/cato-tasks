MySQL Connection and Query
=============

This example will connect to a MySQL database, perform a SQL select query and populate variable arrays with the results. It utilizes the internal Cato database for the example.

This task sample is meant to show the use of the New Connection command, Shared Credentials, Execute SQL command and populating variable arrays from results.

Prerequisites
-------------

You will need to setup a Shared Credential to connect to the internal Cato MySQL database. For this example we will use the "catoread" user which is created by default during install. 

To create a Shared Credential, in the Cato user interface menu, navigate to **Security**, **Manage Shared Credentials**. Click the **Create** button and fill in the following:

    * Name = dbuser
    * Username = catoread
    * Password = catoread
    * Password Confirm = catoread

Click the Save button to finish creating the Shared Credential. 

The task assumes a "Single Server" Cato install, meaning the Task Engine server resides on the same operating system instance as the database server. If this is not the case, you will need to modify the task and change the "localhost" address to the address of the Cato database.

Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

The **New Connection** command in the first step will establish a connection to the MySQL database. The New Connection command supports various connection types which can be viewed by selecting the **Connect Via** drop down list. 

In the text box below, various parameters can be passed to the command. Typically the values passed will be variable, however in this example the parameters are hardcoded.

The following is a list of the parameters available to use with New Connection:

    * address
    * userid
    * password
    * port
    * db_name
    * shared_cred
    * protocol

The different connections types will rely on different parameters. For example, ssh won't require db_name, but does require address.

In this example, we are using the **shared_cred** parameter. You should have created a Shared Credential in the Prerequisite section above. A shared credential is an alias that points to a user id and password so that user ids and password don't need to be stored in tasks or in retrieved and placed in variables. Using shared credentials allows the passwords to be safely stored at rest in an encrypted format. It also makes it easier to change user ids and passwords that may be used on various systems.

Notice the New Connection command has CONN1 in the box next to "as:". This is the connection name which will be used in later steps. This allows you to make several connections to various systems in the same task and refer to their alias as needed.

The **next step** is an Execute SQL command. Notice we are refering to the connection named CONN1 which was created above. The **Mode** is SQL. At this time the other Modes are not yet supported, but plans are in the works to support the other various modes, mainly for Oracle database connections. 

In the SQL box is a simple select statement that will be run against the Cato database. As a general note, this SQL could be a select, update, insert, delete, etc. as needed for the execution of a task.

Now click on the **Variables** button below the select statement. This will show the variables that will be populated after the select statement has run. Clicking on the **Manage Variables** link will popup a window that will let you add, modify or delete the variables that will be populated. 

NOTE: when populating variables, the column position starts at 1, not 0 like in many programming languages.

When the select statement is run and variables are populated, if there is more than one row an array will be defined and each variable will hold the results in the array.

The **if** step will test the taskinstance array variable and print out a **Log** statement based on the count in the array. Notice the syntax for getting an array count.

```
[[taskinstance,*]]
```

The comma and star tell the variable substitution logic to replace the variable with the count instead of an actual value. For more on variable substitution, refer to the Cato wiki page here: https://github.com/cloudsidekick/cato/wiki/task-variables

The **last step** uses the **Drop Connection** command and accepts a connection name as it's parameter. This will close out the connection. This step is unnecessary in this task, but shows an example of closing the connection out. When a task finishes, all connections are dropped. However in a long running task it may make sense to drop and recreate connections as needed.

