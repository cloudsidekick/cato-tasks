vCloud Test Connection
=============

This example shows how to test the connectivity with a vCloud Endpoint

Prerequisites
-------------

A vCloud account and cloud endpoint must be established before running this task. See the following links for more information on setting up an account and cloud endpoint. 

[vCloud Configuration](http://docs.cloudsidekick.com/docs/cato/cloud/vcloud.html)

[Generic Cloud Account Configuration](http://docs.cloudsidekick.com/docs/cato/cloud/cloud-account.html)

[Generic Cloud Endpoint Configuration](http://docs.cloudsidekick.com/docs/cato/cloud/cloud-endpoint.html)

Walkthrough
-----------

Once the vCloud cloud account and endpoint has been configured in the Task Editor, open task **ex-016, Example - vCloud Test Connection**. 

In the lower right corner of the Task Editor, switch the Cloud Account to the vCloud account. This makes this account "in scope" for the browser session. 

On the Run tab, click the Run button. This will kick off the task and the log will popup. 

The first step establishes the connection to the vCloud endpoint. Assuming the account credentials are properly configured, the vCloud endpoint is properly configured and and the vCloud endpoint is the default for the cloud account, the Organization properties will be returned. In the XPath section of the vCloud Call and Parse command, the organization href value will be extracted from the retured XML. This organization href will be used to retrieve a list of virtual datacenters.

The second step prints the org href.

The third step uses the organization href to get a list of available virtual datacenters. The datacenter name and href values will be added to a Task Array which is iterated and printed to the log in the fourth step. 

This simple example shows how to establish a connection to vCloud and can serve as a base for most interactions with vCloud.

References
----------

[VMware vCloud API Reference](http://pubs.vmware.com/vcd-55/topic/com.vmware.vcloud.api.doc_55/GUID-86CA32C2-3753-49B2-A471-1CE460109ADB.html)
