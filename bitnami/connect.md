![](../common/images/customer.logo.png)
---
### ORACLE Cloud Test Drive Event ###
## Connecting to your Ruby instance on the Oracle Compute Cloud ##

First download the SSH keys of your new instance from the Bitnami Console window (ppk and pem files)

![](images/image041.png)

Now make sure you have a ssh tool on your PC.  If you don't have this, you can download [putty](bin/putty.exe) for this.

Use the public IP address of your instance you got from the Bitnami console

![](images/bitnami101.PNG)

Go to the "SSH" and "Auth" menu, and select the private .ppk file you downloaded earlier

![](images/bitnami102.PNG)

when prompted for "login", enter : bitnami

You should now have a command-line on your new instance !

![](images/image043.png)

If you run ifconfig, you will see the private ip of the instance and localhost.  Note that the private ip address is the same as the private ip address of the instance when viewed in the Oracle Cloud Compute console.
+ Take a note of this private IP address

Now execute following commands :
+ Create a directory myapp :  mkdir myapp
+ Move into this directory : cd myapp
+ Now create the new app called "firstapp" in Ruby : rails new firstapp

This will create a directory "firstapp", containing a skeleton rails application.

![](images/image045.png)

Start the application, substituting the private ip address of your VM for the binding:

+ Move into the firstapp directory : cd firstapp
+ Start the new application using the private IP address for your VM binding : bin/rails server --bind=10.196.165.214

![](images/image047.png)
  
WEBrick should start.
Leave the window open and the server running.

Now go back to your Oracle Cloud Console, 
+ Go to the Compute console:
+ Locate your instance - use the public IP address you received on the Bitnami console

![](images/bitnami001.PNG)

Click on the instance and take a note of its security list.
+ You need to hover over the name of the security list, this will look like "bitnami-rubistack-c22d".

![](images/bitnami002.PNG)

Now we will create a new security application (“e.g. rails- <your-user-id>”) for TCP on port 3000:
+ Go to the "Network" tab on the top of the console
+ Select the "Security Applications" on the left side

![](images/bitnami003.PNG)

+ Hit the "Create Security Application button" and fill in following parameters:
++ Name = rails-<your-user-id>
++ Port Type = TCP
++ Port Range Start = 3000
++ Port Range End = 3000

![](images/bitnami004.PNG)


++ 	Name = rails-<your-user-id>
++	Source: public-internet
•	Destination: security list for your bitnami image (from above)
This should have opened your Bitnami VM to traffic from the internet on port 3000.
Check by browsing to the public ip of your image and port 3000.  You should see the “Riding the Rails” page:
 


