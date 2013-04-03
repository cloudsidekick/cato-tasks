Run Task
=============

This example shows how to setup and use the **Run Task** command to launch child tasks.

The Run Task command will kick off independant task instances that can then be monitored. Use cases for using Run Task may be to run parallel job streams on muliplte servers at one time, to create a workflow of multiple steps, etc. Run Task could be called in a loop to create many processes if need be. 

Prerequisites
-------------

None

Walkthrough
-----------

This example contains two tasks, an A and B. The Run Task A task is the parent task whereas Run Task B is the child that is run from the parent. 

Once the tasks have been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

In the Task Editor, open task **ex-008, Example - Run Task B**. We will take a look at the child task first. 

This is a very simple example task. It simply prints a message and sleeps for a certain number of seconds. Click on the **Parameters** tab and click on the "parameters1" value. This parameter accepts an integer as the number of seconds to sleep and has a default of 20. 

Go ahead and run this task from the **Run** tab. When the log page appears, you will need to click the refresh button over the life of the task run to see it complete. 

Now in the Task Editor, open task **ex-007, Example - Run Task A**. 

The first two steps contain the Run Task command. Both steps call the Run Task B task, but pass in different values. You can see the values by clicking on the "Edit Parameters" link near the bottom of each step. Both pass in variables in the hopefully now familiar double square brace syntax. Both of these values are defined on the Run Task A parameters tab. 

Each of the Run Task steps have a **Task Handle** parameter. This is a name or alias for the child task launched and will be used to refer to each independantly later. 

The **next step** is the **Wait For Tasks** command. This command accepts one or more Task Handles as input and will check the task status of each handle until they are all finished in execution (Completed, Error, Cancelled). 

The **last step** prints out properties of each task handle.

On the **Run** tab, go ahead and run this task. Change the sleep seconds for the B tasks if you would like. When the log appears and begins to execute, you will see that both Run Task commands ran and show a link to each child log. While the Wait For Tasks step is waiting for completion, go ahead and click on one of the child task links. 

The log view will change to show the child log. Not much to see in this demo. However you can click on the **Details** button to see the parent task and a link back to the parent task instance log. Go ahead and return to the parent task log. 

Click the refresh button a few more times until both child tasks finish and the handle information appears in the log. 
