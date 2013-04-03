Parsing Text
=============

This example shows how to populate variables using different variable population rules.

The Parse Text command runs any values found in a text buffer through the variable processor. Buffer parsing also is used on the Command Line, Windows Remote Management and HTTP commands so this serves as an example for those as well.

Prerequisites
-------------

None

Walkthrough
-----------

Once the tasks have been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

In the Task Editor, open task **ex-009, Example - Parsing Text**. 

This basic task first populates a variable with a string. 

In the second step the **Parse Text** command is called. The variable defined in the first step will be substituted and then run through the buffer processor. 

On the Parse Text command, click on the **Variables** button on the bottom of the command. Notice how each of the five variables will be populated from the different rules. Click on the **Manage Variables** link to view the editor for these variables. This example dispays essentially three types of rulesets:

    * Positional - the byte number, either at the beginning or end of the string found
    * Prefix / Suffix - a matching string as either the prefix or suffix
    * Regular Expression - a regular expression match

As is found in the example, you can mix the positional and prefix/suffix rules in a single search. If a rule does not match, the variable gets populated with an empty string as is the case in the last variable.

Positional match includes that byte number in the matched string. For instance if you have a string with 4 characters and your starting position is 2, the matched string will include the second byte. Also, byte positions start at 1, not 0 as is the case in many programming languates.

Prefix / Suffix does not include the matched string in the result. For instance, given the string ABCDE and starting Prefix of B, ending Suffix of E, only CD will appear in the result.

The final step displays the results using the **Log** command.
