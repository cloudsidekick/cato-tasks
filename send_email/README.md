Send Email
=============

This example shows how to use the Send Email command. 

The Send Email command allows you to send an email from a task. This can be used to send alerts, html formatted reports on schedule, or let a user know when some long activity has been completed. Attachments aren't supported at this time but will be in the future. 

Prerequisites
-------------

The **Cato Messenger** needs to be properly configured and tested. See [Messenger Configuration](https://github.com/cloudsidekick/cato/wiki/messenger) for more information on setting up the Cato Messenger. 

Walkthrough
-----------

Once the tasks have been imported, you may notice Comments in the task or Notes on individual steps. Refer to these as well. 

In the Task Editor, open task **ex-010, Example - Send Email**. Notice on the **Parameters** tab the "recipient" input parameter is defined. This parameter accepts a comma delimited list of email addresses and will be required.

On the single Send Email step there is the familiar To and Subject fields. The Body accepts any text and variable substitution will be performed prior to the message being sent. In this example, notice the html formatting that is being used. This is helpful for creating reports or making information stand out in the email. Messages are sent using both html and plain text mime types so depending on the recipient's email reader the messages may appear with the formatting or without.

When an email is sent from the **Task Engine**, it is inserted into the Cato database and the task engine moves on. The **Messenger** process picks up the email message and attempts to send it. If sending the email fails, it will continue to retry until it either succeeds or hits the upper limit on retries. This limit is configurable. 

Go ahead and run the task, sending the email to yourself. If the messenger is configured properly you should see the message in your inbox soon. 

To view a list of messages, their status and any errors that may have occurred, navigate to **Information** > **View System Status** in the Cato menu. You can see all of the Cato processes and their heartbeats, including the Messenger. Below you will see a list of the email message attempts made by the Messenger and any error that may have occurred. 

