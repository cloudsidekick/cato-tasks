Input Parameters
=============

This example shows how to setup and use **Input Parameters** as input variables to tasks.

Input Parameters are basically prompts to the end user when a task is run from the UI or via the web service api / command line. Parameters can be referenced like variables in the task execution.

Prerequisites
-------------

None

Walkthrough
-----------

Once the task has been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

In the Task Editor, open task **ex-006, Example Input Parameters**. Click on the **Parameters** tab in the upper left. 

Here you will find the Parameters predefined for this task with their default values. Click on each of the parameter names to view their properties. Here is a description of each:

    * parameter1 - the most basic parameter prompt. The user is required to fill in a value at runtime and can be any value (no constraints).
    * parameter2 - another example of a single value prompt. Has a size constraint, string length.
    * parameter3 - this is a drop down list box prompt. The first one in the list will be the default. 
    * parameter4 - this is a list prompt. the user can add to or remove from the list and the values will be passed to the task as a variable array.
    * parameter5 - this parameter prompt for a value and masks the input. It will pass the value to the task engine encrypted which can then be used in the task. Useful for passwords and such. 
    * parameter6 - an example of a regular expression constraint. The constrain help is displayed to the user if they enter a value that doesn't match the rule.

When the user is presented with the parameters, they will have the option of overriding the default values. 

For **Constraints** Min and Max Length are self-explanatory. Min and Max Value are for integers only. The constraint box accepts a regular expression stringand will test the input parameter value that the user inputs and reprompt the user if it does not match the regular expression. 

Now let's look at the task steps themselves. The first **Log** step displays the parameters in the log. Parameter5 will automatically be decrypted. Notice that the syntax to dereference parameters is the same as the regular Cato variable syntax. That's because they are essentially the same thing. Also notice that variable names are not case senstitive.

The second and third steps display the count of parameter4 and loop through the values of the array. 

Run the task via the **Run** tab. All of the parameters are displayed and can be overridden. If there are more that can fit in the window size, you may need to scroll down to see the rest. Change some of the values and click Run Now. The log will popup and display the output. 

Re-run the task. Notice how the default values are displayed. Above the parameters on the left, select "Previous Values". This will change the parameter defaults to whatever you used last time. Rerun the task and observe the output.
