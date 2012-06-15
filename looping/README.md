Looping and Variable Arrays
=============

This example task demonstrates setting variables, using variables and using looping. 

Walkthrough
-----------

The **first step** sets an array named z with 5 different values. Make note that variable array indices start a 1, not 0 (zero) as most languages use.

Notice the use of the modifiers. Modifiers change the values before they are stored. 

Also in the first step the variable y is set. When no index is used, 1 is assumed. A variable is really an array of one. 


The **second step** is a Loop command. The counter variable is the variable that holds the loop iteration number. 

The loop will continue until the condition 

    [[z,*]]

 is met. First the square brackets signify variable substitution. Secondly, the comma star tell the task engine to get the total elements in the array z. In this example:

    [[z,*]] = 5

So the loop will iterate 5 times.  

In the "Action" section of the Loop command, the Log command is used. This will insert a variable substituted message into the database. 

In the Log box

... needs to be continued ...
