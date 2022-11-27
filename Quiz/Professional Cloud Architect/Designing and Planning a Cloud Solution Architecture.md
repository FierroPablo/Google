
1.
Cymbal Direct is working with Cymbal Retail, a separate, autonomous division of Cymbal with different staff, networking teams, and data center. Cymbal Direct and Cymbal Retail are not in the same Google Cloud organization. Cymbal Retail needs access to Cymbal Direct’s web application for making bulk orders, but the application will not be available on the public internet. You want to ensure that Cymbal Retail has access to your application with low latency. You also want to avoid egress network charges if possible. What should you do?

**-Verify that the subnet range Cymbal Retail is using doesn’t overlap with Cymbal Direct’s subnet range, and then enable VPC Network Peering for the project.**
(Correct! VPC Peering allows for shared networking between organizations.)
-Specify Cymbal Direct’s project as the Shared VPC host project, and then configure Cymbal Retail’s project as a service project.
-If Cymbal Retail does not have access to a Google Cloud data center, use Carrier Peering to connect the two networks.
-Verify that the subnet Cymbal Retail is using has the same IP address range with Cymbal Direct’s subnet range, and then enable VPC Network Peering for the project.

2.
You are working with a client who is using Google Kubernetes Engine (GKE) to migrate applications from a virtual machine–based environment to a microservices-based architecture. Your client has a complex legacy application that stores a significant amount of data on the file system of its VM. You do not want to re-write the application to use an external service to store the file system data. What should you do?

In Cloud Shell, create a YAML file defining your Deployment called deployment.yaml. Create a Deployment in GKE by running the command kubectl apply -f deployment.yaml
(Incorrect. A Deployment represents multiple identical Pods. A Deployment is used to ensure that Pods are available, but it does not attempt to maintain state. Containers are considered disposable. The kubectl command can be used from gcloud to create or modify deployments defined in a YAML file or manifest.)

**In Cloud Shell, create a YAML file defining your StatefulSet called statefulset.yaml. Create a StatefulSet in GKE by running the command kubectl apply -f statefulset.yaml**
(Correct! A StatefulSet represents a group of persistent Pods. The YAML file will define a PersistentVolumeClaim (PVC) that allows for an application to retain state. A StatefulSet is commonly used with applications like databases.)

In Cloud Shell, create a YAML file defining your Container called build.yaml. Create a Container in GKE by running the command gcloud builds submit –config build.yaml .

In Cloud Shell, create a YAML file defining your Pod called pod.yaml. Create a Pod in GKE by running the command kubectl apply -f pod.yaml
(Incorrect. A Pod is the smallest unit of Deployment and contains one or more containers. A Pod doesn’t define how many containers must be running, so they’re generally managed by the Deployment or StatefulSet.)

3.
You are working in a mixed environment of VMs and Kubernetes. Some of your resources are on-premises, and some are in Google Cloud. Using containers as a part of your CI/CD pipeline has sped up releases significantly. You want to start migrating some of those VMs to containers so you can get similar benefits. You want to automate the migration process where possible. What should you do?

**Manually create a GKE cluster, and then use Migrate for Anthos to set up the cluster, import VMs, and convert them to containers.**
(Correct. You must initially create a GKE cluster. Then you can use Migrate for Anthos to set up the cluster and import the VMs.)

Manually create a GKE cluster. Use Cloud Build to import VMs and convert them to containers.

Use Migrate for Anthos to automate the creation of Compute Engine instances to import VMs and convert them to containers.

Use Migrate for Compute Engine to import VMs and convert them to containers.

4.
Cymbal Direct is evaluating database options to store the analytics data from its experimental drone deliveries. You're currently using a small cluster of MongoDB NoSQL database servers. You want to move to a managed NoSQL database service with consistent low latency that can scale throughput seamlessly and can handle the petabytes of data you expect after expanding to additional markets. What should you do?

Extract the data from MongoDB. Insert the data into Firestore using Datastore mode.
(Incorrect. Firestore does not meet the requirements for consistent low latency, scaling throughput seamlessly, and petabyte-scaling data.)

Extract the data from MongoDB. Insert the data into Firestore using Native mode.

**Create a Bigtable instance, extract the data from MongoDB, and insert the data into Bigtable.**
(Correct! Bigtable is ideal for IoT, gives consistently sub-10ms latency, and can be used at a petabyte scale.)

Extract the data from MongoDB, and insert the data into BigQuery.
(Incorrect. BigQuery is used for Enterprise data warehouse and building reports and extracting insights. Bigtable meets the requirements for consistent low latency, scaling throughput seamlessly, and petabyte-scale.)

5.
Customers need to have a good experience when accessing your web application so they will continue to use your service. You want to define key performance indicators (KPIs) to establish a service level objective (SLO). Which KPI could you use?

Eighty-five percent of customers are satisfied users
(Incorrect. KPIs must be specific and measurable. ‘Satisfied’ is not specific, and the KPI is not bounded by a period of time.)

Low latency for > 85% of requests when aggregated over 1 minute
(Incorrect. KPIs must be specific and measurable. The word ‘low’ does not provide enough information to determine whether latency is acceptable. You should be able to compare your measurement against a threshold value to determine whether it is acceptable.)

**Eighty-five percent of requests succeed when aggregated over 1 minute**
(Correct! This is specific, and you can reasonably expect to meet this KPI.)

Eighty-five percent of requests are successful
(Incorrect. This KPI is not bounded by time. You could have 100% success during one period of time and 75% during another, but the average (87.5) uptime would exceed the KPI.)

6.
Cymbal Direct has created a proof of concept for a social integration service that highlights images of its products from social media. The proof of concept is a monolithic application running on a single SuSE Linux virtual machine (VM). The current version requires increasing the VM’s CPU and RAM in order to scale. You would like to refactor the VM so that you can scale out instead of scaling up. What should you do?

Move the existing codebase and VM provisioning scripts to git, and attach external persistent volumes to the VMs.
(Incorrect. Version control allows for change control. Backing services allow for flexibility in design, not concurrency.)

Make sure that the application declares any dependent requirements in a requirements.txt or equivalent statement so that they can be referenced in a startup script, and attach external persistent volumes to the VMs.

Make sure that the application declares any dependent requirements in a requirements.txt or equivalent statement so that they can be referenced in a startup script. Specify the startup script in a managed instance group template, and use an autoscaling policy.

**Use containers instead of VMs, and use a GKE autoscaling deployment.**
(Correct! Treating each app as one or more stateless processes means externalizing state to a separate database service. This allows for more concurrent processing.)

7.
Cymbal Direct's employees will use Google Workspace. Your current on-premises network cannot meet the requirements to connect to Google's public infrastructure. What should you do?

Order a Dedicated Interconnect from a Google Cloud partner, and ensure that proper routes are configured.
(Incorrect. A Dedicated Interconnect connects a data center to your VPC.)

Order a Partner Interconnect from a Google Cloud partner, and ensure that proper routes are configured.
(Incorrect. A Partner Interconnect allows access to your VPC network via a partner.This would allow access between on-premises and your internal IP addresses, which greatly exceeds the scope and does not follow the principle of least privilege.)

Connect the network to a Google point of presence, and enable Direct Peering.

**Connect the on-premises network to Google’s public infrastructure via a partner that supports Carrier Peering.**
(Correct! Carrier Peering allows using a Google partner to connect to Google public infrastructure, such as Workspace or YouTube.)

8.
Cymbal Direct drones continuously send data during deliveries. You need to process and analyze the incoming telemetry data. After processing, the data should be retained, but it will only be accessed once every month or two. Your CIO has issued a directive to incorporate managed services wherever possible. You want a cost-effective solution to process the incoming streams of data. What should you do?

Ingest data with IoT Core, process it with Dataprep, and store it in a Coldline Cloud Storage bucket.
(Incorrect. Dataprep is used to normalize data before processing, if necessary. Coldline could be used, but Nearline is probably a better fit because the data could be accessed every month. Coldline has a higher cost for data access than Nearline, which makes it a poor choice for data accessed “every month or two.”)

Ingest data with IoT Core, and then publish to Pub/Sub. Use BigQuery to process the data, and store it in a Standard Cloud Storage bucket.

**Ingest data with IoT Core, and then publish to Pub/Sub. Use Dataflow to process the data, and store it in a Nearline Cloud Storage bucket.**
(Correct! Dataflow is a fully managed service that can be used to process both streams and batches of data. Nearline is a good fit because the data could be accessed every month.)

Ingest data with IoT Core, and then store it in BigQuery.

9.
Cymbal Direct developers have written a new application. Based on initial usage estimates, you decide to run the application on Compute Engine instances with 15 Gb of RAM and 4 CPUs. These instances store persistent data locally. After the application runs for several months, historical data indicates that the application requires 30 Gb of RAM. Cymbal Direct management wants you to make adjustments that will minimize costs. What should you do?

Stop the instance, and then use the command gcloud compute instances set-machine-type VM_NAME --machine-type e2-standard-8. Start the instance again.
(Incorrect. An e2-standard-8 instance will have the appropriate amount of memory. However, this instance type will have more CPU than necessary and incur additional unnecessary costs.)

**Stop the instance, and then use the command gcloud compute instances set-machine-type VM_NAME --machine-type 2-custom-4-30720. Start the instance again.**
(Correct! Custom instances are a good way to optimize costs. You don’t have to pay for resources you don’t need.)

Stop the instance, and then use the command gcloud compute instances set-machine-type VM_NAME --machine-type e2-standard-8. Set the instance’s metadata to: preemptible: true. Start the instance again.

Stop the instance, and then use the command gcloud compute instances set-machine-type VM_NAME --machine-type 2-custom-4-30720. Set the instance’s metadata to: preemptible: true. Start the instance again.
(Incorrect. Although preemptible instances can save substantial money, they are not appropriate for instances that need to store persistent data locally.)

10.
You are creating a new project. You plan to set up a Dedicated interconnect between two of your data centers in the near future and want to ensure that your resources are only deployed to the same regions where your data centers are located. You need to make sure that you don’t have any overlapping IP addresses that could cause conflicts when you set up the interconnect. You want to use RFC 1918 class B address space. What should you do?

Create a new project, leave the default network in place, and then use the default 10.x.x.x network range to create subnets in your desired regions.
(Incorrect. Default mode networks create subnets for you automatically in each zone and could allow people to accidentally provision resources in other regions.)

**Create a new project, delete the default VPC network, set up a custom mode VPC network, and then use IP addresses in the 172.16.x.x address range to create subnets in your desired regions.**
(Correct! Custom networks give you full control.)

Create a new project, delete the default VPC network, set up an auto mode VPC network, and then use the default 10.x.x.x network range to create subnets in your desired regions.

Create a new project, delete the default VPC network, set up the network in custom mode, and then use IP addresses in the 192.168.x.x address range to create subnets in your desired zones. Use VPC Network Peering to connect the zones in the same region to create regional networks.
