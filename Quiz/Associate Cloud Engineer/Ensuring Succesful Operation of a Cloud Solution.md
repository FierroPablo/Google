1.
Which of the following tasks are part of the process when configuring a managed instance group? (Pick two).

Choosing instance Machine type
(Incorrect. This is part of your instance template definition.)

**Providing Number of instances**
(Correct! Number of instances is part of your managed instance group configuration.)

Configuring the operating system
(Incorrect. This is part of your instance template definition.)

**Defining Health checks**
(Correct! Health checks are part of your managed instance group configuration.)

Specifying Persistent disks


2.
What is the declarative way to initialize and update Kubernetes objects?

kubectl run
(Incorrect. kubectl run creates a Kubernetes object in an imperative way using arguments you specify on the command line.)

kubectl create

**kubectl apply**
(Correct! kubectl apply creates and updates Kubernetes objects in a declarative way from manifest files.)

kubectl replace


3.
You want to view a description of your available snapshots using the command line interface (CLI). What gcloud command should you use?

gcloud compute list snapshots
(Incorrect. Snapshots is a compute command subgroup. It needs to come before the list command.)

gcloud snapshots list

**gcloud compute snapshots list**
(Correct! gcloud commands are built with groups and subgroups, followed by a command, which is a verb. In this example, Compute is the Group, snapshots is the subgroup, and list is the command.)

gcloud compute snapshots get


4.
You have a scheduled snapshot you are trying to delete, but the operation returns an error. What should you do to resolve this problem?

Restore the snapshot to a persistent disk before deleting it.
(Incorrect. This does not allow you to delete a scheduled snapshot.)

Delete the object the snapshot was created from.

Delete the downstream incremental snapshots before deleting the main reference.
(Incorrect. This is not required to delete a scheduled snapshot and would be a lot of manual work.)

**Detach the snapshot schedule before deleting it.**
(Correct! You can’t delete a snapshot schedule that is still attached to a persistent disk.)


5.
You want to implement a lifecycle rule that changes your storage type from standard to nearline after a specific date. What conditions should you use? (Pick two).

IsLive
(Incorrect. IsLive has to do with whether or not the object you are looking at is the latest version. It is not date-based.)

**CreatedBefore**
(Correct! CreatedBefore lets you specify a date.)

NumberofNewerVersions
(Incorrect. NumberofNewerVersions is based on object versioning and you don’t specify a date.)

Age

**MatchesStorageClass**
(Correct! MatchesStorageClass is required to look for objects with a standard storage type.)


6.
What Kubernetes object provides access to logic running in your cluster via endpoints that you define?

Deployments
(Incorrect. Deployments help you with availability and the health of a set of pod replicas. They do not help you configure external access.)

Pods

Pod templates

**Services**
(Correct! Service endpoints are defined by pods with labels that match those specified in the service configuration file. Services then specify how those pods are exposed.)


7.
Cymbal Superstore has a subnetwork called mysubnet with an IP range of 10.1.2.0/24. You need to expand this subnet to include enough IP addresses for at most 2000 new users or devices. What should you do?

gcloud compute networks subnets expand-ip-range mysubnet --region us-cetnral1 --prefix-length 22
(Incorrect. This command doesn’t give you enough IP addresses (only 1,000).)

gcloud networks subnets expand-ip-range mysubnet --region us-central1 --prefix-length 21

gcloud compute networks subnets expand-ip-range mysubnet --region us-central1 --prefix-length 20

**gcloud compute networks subnets expand-ip-range mysubnet --region us-central1 --prefix-length 21**
(Correct! This command gives a total of 2046 addresses available and meets the requirement.)


8.
Cymbal Superstore’s GKE cluster requires an internal http(s) load balancer. You are creating the configuration files required for this resource. What is the proper setting for this scenario?

Implement custom static routes in your VPC:
(Incorrect. This describes a routes-based cluster. In order to support internal load balancing, your cluster needs to use VPC-native mode, where your cluster provides IP addresses to your pods from an alias IP range.)

Configure your service object with a type: LoadBalancer.
(incorrect. Using Load Balancer at the service level implements a Layer 4 network load balancer, not an http(s) load balancer.)

Annotate your ingress object with an ingress.class of “gce.”
(Incorrect. To implement an internal load balancer, the ingress class needs to be “gce-internal.”)

**Annotate your service object with a neg reference.**
(Correct! This is correct because an internal http(s) load balancer can only use NEGs.)


9.
You have a Cloud Run service with a database backend. You want to limit the number of connections to your database. What should you do?

Set Concurrency settings.
(Incorrect. Concurrency is how many users can connect to a particular instance. It does not directly affect connections to backend services.)

**Set Max instances.**
(Correct! Max instances control costs, keeping you from starting too many instances by limiting your number of connections to a backing service.)

Set Min instances.

Set CPU Utilization.


10.
Cymbal Superstore’s supply chain management system has been deployed and is working well. You are tasked with monitoring the system’s resources so you can react quickly to any problems. You want to ensure the CPU usage of each of your Compute Engine instances in us-central1 remains below 60%. You want an incident created if it exceeds this value for 5 minutes. You need to configure the proper alerting policy for this scenario. What should you do?

**Choose resource type of VM instance and metric of CPU utilization, condition trigger if any time series violates, condition is above, threshold is .60 for 5 minutes.**
(Correct! All the values of this statement match the scenario.)

Choose resource type of VM instance and metric of CPU utilization, condition trigger all time series violates, condition is above, threshold is .60 for 5 minutes.

Choose resource type of VM instance and metric of CPU load, condition trigger if any time series violates, condition is below, threshold is .60, for 5 minutes.
(Incorrect. CPU load is not a percentage, it is a number of processes.)

Choose resource type of VM instance, and metric of CPU utilization, condition trigger if any time series violates, condition is below, threshold is .60 for 5 minutes.
