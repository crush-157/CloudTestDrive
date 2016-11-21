![](../common/images/customer.logo.png)
---
# ORACLE Cloud Test Drive Event#
----
## Deploy a simple Node.js application onto the Application Container Cloud using the GUI##

Start by downloading the [zip file](raw/simple_node/bin/node-server.zip) containing the Node.js artifacts.
Open the file to understand the content of this package : 
+ manifest.json : This file is specific to Application Container Cloud, and specifies how to start your application and the Node.js runtime version to use. Optionally, you can include notes and a release indication. 
+ server.js : the Node.js script running on the server
+ index2.htlm : a html5 script containing client-side javascript calling the server-side application

![](images/node001.PNG)

The zip file contains the four other files – all at the same level in the same directory.
 
Application Management in the Cloud Service Console
It is a simple application and not administration is required hopefully. However, we can do some monitoring, inspection of log files and scaling of the environment. Besides, new versions of the application can be deployed.
The Deployments page is fairly important: here we can define Service Bindings to other Oracle PaaS service instances. Here too, environment variables can be set that can be leveraged inside the Node.js application – using the statement process.env.NAME_OF_VARIABLE (such as process.env.PORT).
Here an example of deploying a new version of the application:
 

 
After clicking the button Upload New, this popup appears:
 

After specifying the new application archive, press OK.
The file is processed:
 

 
and redeployment takes place:
 

Log files are available for inspection. Anything written to the console from the Node.js application can be inspected from these files – that are written to the storage container associated with the JCS instance (I presume). At least I need to provide my Storage Cloud Service credentials in order to download the log file:
 
 
From the downloaded zip-file I can inspect the logs:
 
 


