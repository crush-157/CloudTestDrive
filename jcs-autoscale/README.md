![](../common/images/customer.logo.png)
---
# ORACLE Cloud-Native DevOps workshop #
-----
## Oracle Java Cloud Service Policy Based Auto Scaling ##

### Introduction ###
Scaling lets you add or remove resources for an Oracle Java Cloud Service instance on demand in response to changes in load on the service instance. You can scale an Oracle Java Cloud Service instance by scaling a cluster, a node, or the Coherence data tier in the service instance.
Oracle Java Cloud Service has Auto Scaling feature which allows you to define rule for a given service. When the rule's criteria meets the defined threshold Auto Scaling starts to scale in/out the service.

### About this tutorial ###
This tutorial demonstrates how to:

+ Create Auto Scaling rule

### Prerequisites ###

+ Oracle Public Cloud Services account including:
	+ Database Cloud Service
	+ Java Cloud Service
If you are taking part in the Cloud Test Drive Event, you already should have a running DB and Java Cloud Service in your environment

### Steps ###


#### Create Auto Scaling Rule ####

Create rule for Java Cloud Service which triggers auto scaling based on the defined criteria. Go to the Java Cloud Service instance details page and click **Topology** on the left menu. Click **Add Node** and select **Auto Scaling** item.
![](images/25.topology.add.node.png)

On the Rules page click **Create Rule**. 
![](images/26.create.rule.png)

Define the rule parameters.
	
+ Perform: **Scale Out**
+ Maximum Cluster Size: **2** (1 more higher then the existing cluster size)
+ CPU Utilization: **Average** - **50%**
+ Number for measurement period: **1**
+ Period length: **5** minutes (this is the minimum)
+ VM instances: **Any**
+ Cool down period: 30 (this is the minimum)

Click **Create**.

![](images/27.rule.details.png)

Wait till the rule will be complete.
![](images/27.rule.ready.png)

                                               


