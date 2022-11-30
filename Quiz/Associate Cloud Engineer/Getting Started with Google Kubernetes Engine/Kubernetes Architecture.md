1.
What is the difference between a pod and a container?

A. A container contains one or more pods.
_Incorrect._

**B. A pod contains one or more containers.**
_Feedback: The pods within a container are tightly coupled with one another and can ommunicate using the localhost IP address._

C. Pods and containers are two names for the name thing.
_Incorrect._


2.
You are designing an application, and you want to ensure that the containers are located s close to each other as possible, in order to minimize latency. Which design decision elps meet this requirement?

A. Give the containers the same labels.
_Feedback: Review the lesson on Kubernetes Concepts._

B. Place the containers in the same cluster.
_Feedback: Review the lesson on Kubernetes Concepts._

C. Place the containers in the same Namespace.
_Feedback: Review the lesson on Kubernetes Concepts._

**D. Place the containers in the same Pod.**
_Feedback: Placing containers in the same Pod ensures they are scheduled together on the same node, minimizing latency._


3.
Which Kubernetes component does the kubectl command connect to in order to carry out operations on a cluster?

**A. kube-apiserver**
_Correct._

B. kube-controller-manager
_Feedback: Review the lesson on Kubernetes Concepts._

C. kube-dns
_Feedback: Review the lesson on Kubernetes Concepts._

D. kube-scheduler
_Feedback: Review the lesson on Kubernetes Concepts._


4.
Which control plane component is the only one with which clients interact directly?

A. etcd
_Incorrect._

**B. kube-apiserver**
_Correct._

C. kube-controller-manager
_Incorrect._

D. kube-scheduler
_Incorrect._


5.
Which control plane component is the cluster's database?

**A. etcd**
_Correct._

B. kube-apiserver
_Incorrect._

C. kube-controller-manager
_Incorrect._

D. kube-scheduler
_Incorrect._


6.
What is the role of the kubelet?

A. To interact with underlying cloud providers.
_Incorrect._

B. To maintain network connectivity among the Pods in a cluster.
_Incorrect._

**C. To serve as Kubernetes’s agent on each node.**
_Correct._


7.
In GKE clusters, how are nodes provisioned?

A. As abstract parts of the GKE service that are not exposed to Google Cloud customers.
_Incorrect._

**B. As Compute Engine virtual machines.**
_Correct._


8.
In GKE, how are control planes provisioned?

**A. As abstract parts of the GKE service that are not exposed to Google Cloud customers.**
_Correct._

B. As Compute Engine virtual machines.
_Incorrect_


9.
What is the purpose of configuring a regional cluster in GKE?

**A. To allow applications running in the cluster to withstand the loss of a zone.**
_Correct._

B. To ensure that the cluster's workloads are isolated from the public Internet.
_Feedback: Private clusters ensure that the cluster's workloads are isolated from the public Internet._


10.
You have deployed a new Kubernetes Engine regional cluster with four machines in the default pool for the first zone and left the number of zones at the default. How many Compute Engine machines are deployed and billed against your account?

A. Fifteen. (Four nodes and a single control plane are deployed to each of the three zones. A control plane node is deployed in each zone and it is billed against your account.)
_Feedback: Review the lesson on GKE Concepts._

B. Sixteen. (Four nodes are deployed in primary and secondary zones in two regions, for a total of 4 zones and 16 nodes. A control plane node is deployed in each zone but it is not billed to your account.)
_Feedback: Review the lesson on GKE Concepts._

C. Ten. (Four nodes are deployed in the first zone and three nodes are deployed in two other zones because you selected the defaults.)
_Feedback: Review the lesson on GKE Concepts._

**D. Twelve. (Four nodes are deployed in each of three zones. A control plane node is deployed in each zone which is indirectly billed against your account through the cluster management fee.)**


11.
In a manifest file for a Pod, in which field do you define a container image for the Pod?

A. apiVersion
_Feedback: ApiVersion describes which Kubernetes API version is used to create the object._

B. kind
_Feedback: Kind tells Kubernetes which object we want._

C. metadata
_Feedback: The metadata helps identify an object by supplying it with a name and one or more labels._

**D. spec**


12.
What are Kubernetes namespaces useful for? Choose all that are correct (2 correct answers).

**A. Namespaces allow you to use object names that would otherwise be duplicates of one another.**
_Correct._

**B. Namespaces let you implement resource quotas across your cluster.**
_Correct._

C. Namespaces make resources more secure.
_Feedback: By themselves, using namespaces does not increase security._

D. Namespaces partition Linux kernel resources.
_Feedback: Linux namespaces are not the same as Kubernetes namespaces._


13.
What is the purpose of the Deployment object?

A. To ensure that a defined set of Pods is running at any given time.
_Correct._

B. To launch one or more Pods and ensure that a specified number of them successfully run to completion and exit.
_Feedback: This option describes a Kubernetes Job._

C. To launch one or more Pods on a time-based schedule.
_Feedback: This option describes a Kubernetes CronJob._


14.
If you are deploying applications in your Pods that need persistent storage, which controller type should you use?

A. DaemonSet
_Incorrect._

B. Deployment
_Incorrect._

C. ReplicaSet
_Incorrect._

**D. StatefulSet**
_Correct._


15.
You need to ensure that the production applications running on your Kubernetes cluster are not impacted by test and staging deployments. Which features should you implement and configure to ensure that the resources for your production applications can be prioritized?

A. Configure labels for Test, Staging and Production and configure specific Kubernetes resource quotas for the Production Namespace.
_Feedback: Review the lesson on Kubernetes Object Management._

B. Configure Namespaces for Test, Staging and Production and configure specific Kubernetes resource quotas for the Production Namespace.
_Feedback: Review the lesson on Kubernetes Object Management._

**C. Configure Namespaces for Test, Staging and Production and configure specific Kubernetes resource quotas for the test and staging Namespaces.**
_Feedback: Resource quotas are used to limit usage in specific Namespaces, and do not need to be configured for all Namespaces, only those you need to limit._

D. Configure resource requests for Test, Staging and Production and configure specific Kubernetes resource quotas for the Production Namespace.
_Feedback: Review the lesson on Kubernetes Object Management._


16.
When configuring storage for stateful applications, what steps must you take to provide file system storage inside your containers for data from your applications that will not be lost or deleted if your Pods fail or are deleted for any reason?

A. You must create Volumes using local Storage on the Nodes and mount the Volumes inside your containers to provide durable storage.
_Feedback: Review the lesson on Kubernetes Object Management._

**B. You must create Volumes using network based storage to provide durable storage remote to the Pods and specify these in the Pods.**
_Correct._

C. You must export the data from your applications to a remote service that preserves your data.
_Feedback: Review the lesson on Kubernetes Object Management._

D. You must mount NFS Volumes on each container in the Pod that requires durable storage.
_Feedback: Review the lesson on Kubernetes Object Management._


17.
You have a new logging and auditing utility that you need to deploy on all of the nodes within your cluster. Which type of controller should you use to handle this task?

**A. DaemonSet**
_Correct._

B. Deployment
_Feedback: Review the lesson on Kubernetes Object Management._

C. ReplicaSet
_Feedback: Review the lesson on Kubernetes Object Management._

D. StatefulSet
_Feedback: Review the lesson on Kubernetes Object Management._


18.
You want to deploy multiple copies of your application, so that you can load balance traffic across them. How should you deploy this application's Pods to the production Namespace in your cluster?

**A. Create a Deployment manifest that specifies the number of replicas that you want to run.**
_Correct._

B. Create a Service manifest for the LoadBalancer that specifies the number of replicas you want to run.
_Feedback: Review the lesson on Kubernetes Object Management._

C. Create separate named Pod manifests for each instance of the application and deploy as many as you need.
_Feedback: Review the lesson on Kubernetes Object Management._

D. Deploy the Pod manifest multiple times until you have achieved the number of replicas required.
_Feedback: Review the lesson on Kubernetes Object Management._
