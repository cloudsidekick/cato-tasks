Looping and Variable Arrays
=============

This example task demonstrates setting variables, using variables and using looping. 

Walkthrough
-----------

The **first step** sets an array named z with 5 different values. Make note that variable array indices start a 1, not 0 (zero) as most languages use.

Notice the use of the modifiers. Modifiers change the values before they are stored. 

Also in the first step the variable y is set. When no index is used, 1 is assumed. A variable is really an array of one. 


The **second step** is a Loop command. The counter variable is the variable that holds the loop iteration number. In this case the counter variable is a. 

The loop will continue until the condition 

    [[z,*]]

 is met. First the square brackets signify variable substitution. Secondly, the comma star tell the task engine to get the total elements in the array z. In this example:

    [[z,*]] = 5

So the loop will iterate 5 times.  

In the "Action" section of the Loop command, the Log command is used. This will insert a variable substituted message into the database. 

In the Log box we see more variable substitution. 

    [[y]]

will substiture for the word "number".

The variable syntax:

    [[z,[[a]]]]

says "substitute the variable z, of index a". In other words z is the array and to the right of the comma is the index. "a" is the counter variable of the loop and will get incremented each time through the loop.

*Note* - Mentioned before, but Cato array indexes start with 1, not 0. 


The **next step** is an example of a loop interating through a fixed number of times, in this case 100 times. The counter variable "b" will be substituted and printed out in the log. 
