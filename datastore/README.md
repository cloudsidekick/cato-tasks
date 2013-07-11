Datastore
=============

This example shows how to use the Cato internal datastore to store and retrieve custom data to your application. 

The Cato datastore is a MongoDB backed NOSQL database the is packaged with the Cato install. MongoDB is a schema-less json document database that can be used to store a variety of information. Is is an option to use with Cato for custom application data such as application or server state information, lookup values, application settings, etc. The flexibility of the NOSQL architecture allows for user defined data schemas that can change as the needs change. 

Specifically within Cato, task commands are available that hide much of the complexity of establishing the connection, managing the schema and updating data. Updating and retrieving data is fast which is important when there are several tasks reading and writing data at the same time. 

Prerequisites
-------------

None

Walkthrough
-----------

There are two tasks with this example, **ex-013, Example - Create and Insert Datastore**, and **ex-014, Example Query Datastore**. Once the tasks have been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. **ex-013** is the main task, **ex-014** is called as a subtask.

Start by openning **ex-013, Example - Create and Insert Datastore** in the task editor. The first two steps setup our example data. In **Step 1**, we have a command delimited list of server names and addresses. The simulated use case is a set of servers with fixed ip addresses in a data center that may be available for testing purposes. The second sample task will simulate retrieving servers that are not in use, flagging them as in use and using them in testing. **Set Variable** is used to setup this data.

**Step 2** parses the comma delimited data, chopping the data into rows and columns, server name in column 1, address in column 2. On the **Parse Text** command, click on the Variables button to see the variable names and delimiter values used. In the Text box, the "serverlist" variable will be substituted at runtime.

More to come on each step here..

Run Example
-----------

Run **ex-013, Example - Create and Insert Datastore** and view the output.
