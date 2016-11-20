
## Introduction##

This script will guide you through the steps to connnect into the Ruby instance you jusst created.  For this  you will need a ssh shell on your PC.


Then you can download the key and ssh into it
If you run ifconfig, you will see the private ip of the instance and localhost.  Note that the private ip address is the same as the private ip address of the instance when viewed in the Oracle Cloud Compute console.
Create a directory myapp, and cd into it.  Then run:
$rails new firstapp
This will create a directory firstapp, containing a skeleton rails application.
 
Start the application, substituting the private ip address of your VM for the binding:
 
WEBrick should start.
Leave the window open and the server running.
In the OPC console:
Find your instance (private IP is probably easiest way)
Click on the instance and take a note of its security list.
Create a new security application (“e.g. rails- <your-user-id>”) for TCP on port 3000
Create a new security rule (“e.g. rails-<your-user-id>”):
•	Application = rails-<your-user-id>
•	Source: public-internet
•	Destination: security list for your bitnami image (from above)
This should have opened your Bitnami VM to traffic from the internet on port 3000.
Check by browsing to the public ip of your image and port 3000.  You should see the “Riding the Rails” page:
 


