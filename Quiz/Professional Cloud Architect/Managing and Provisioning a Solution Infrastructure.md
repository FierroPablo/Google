1.
Your existing application runs on Ubuntu Linux VMs in an on-premises hypervisor. You want to deploy the application to Google Cloud with minimal refactoring. What should you do?

Set up a Google Kubernetes Engine (GKE) cluster, and then create a deployment with an autoscaler.

Use a Dedicated or Partner Interconnect to connect the on-premises network where your application is running to your VPC: Configure an endpoint for a global external HTTP(S) load balancer that connects to the existing VMs.

Write Terraform scripts to deploy the application as Compute Engine instances.

Isolate the core features that the application provides. Use App Engine to deploy each feature independently as a microservice.


2.
Cymbal Direct wants to allow partners to make orders programmatically, without having to speak on the phone with an agent. What should you consider when designing the API?

The API backend should be loosely coupled. Clients should not be required to know too many details of the services they use. REST APIs using gRPC should be used for all external APIs.

The API backend should be loosely coupled. Clients should not be required to know too many details of the services they use. For REST APIs, HTTP(S) is the most common protocol.

The API backend should be tightly coupled. Clients should know a significant amount about the services they use. For REST APIs, HTTP(S) is the most common protocol used.

The API backend should be tightly coupled. Clients should know a significant amount about the services they use. REST APIs using gRPC should be used for all external APIs.


3.
Cymbal Direct wants a layered approach to security when setting up Compute Engine instances. What are some options you could use to make your Compute Engine instances more secure?

Use labels to allow traffic only from certain sources and ports. Turn on Secure boot and vTPM.

Use network tags to allow traffic only from certain sources and ports. Turn on Secure boot and vTPM.

Use network tags to allow traffic only from certain sources and ports. Use a Compute Engine service account.

Use labels to allow traffic only from certain sources and ports. Use a Compute Engine service account.


4.
Cymbal Direct must meet compliance requirements. You need to ensure that employees with valid accounts cannot access their VPC network from locations outside of its secure corporate network, including from home. You also want a high degree of visibility into network traffic for auditing and forensics purposes. What should you do?

Ensure that all users install Cloud VPN. Enable VPC Flow Logs for the networks you need to monitor.

Enable Identity-Aware Proxy (IAP) to allow users to access services securely. Use Google Cloud’s operations suite to view audit logs for the networks you need to monitor.

Enable VPC Service Controls, and use Google Cloud’s operations suite to view audit logs for the networks you need to monitor.

Enable VPC Service Controls, define a network perimeter to restrict access to authorized networks, and enable VPC Flow Logs for the networks you need to monitor.


5.
Cymbal Direct needs to use a tool to deploy its infrastructure. You want something that allows for repeatable deployment processes, uses a declarative language, and allows parallel deployment. You also want to deploy infrastructure as code on Google Cloud and other cloud providers. What should you do?

Automate the deployment with Terraform scripts.

Use Google Kubernetes Engine (GKE) to create deployments and manifests for your applications.

Develop in Docker containers for portability and ease of deployment.

Automate the deployment with Cloud Deployment Manager.


6.
Cymbal Direct wants to create a pipeline to automate the building of new application releases. What sequence of steps should you use?

Set up a source code repository. Run unit tests. Check in code. Deploy. Build a Docker container.

Set up a source code repository. Check in code. Run unit tests. Build a Docker container. Deploy.

Run unit tests. Deploy. Build a Docker container. Check in code. Set up a source code repository.

Check in code. Set up a source code repository. Run unit tests. Deploy. Build a Docker container.


7.
You need to deploy a load balancer for a web-based application with multiple backends in different regions. You want to direct traffic to the backend closest to the end user, but also to different backends based on the URL the user is accessing. Which of the following could be used to implement this?

The request is received by the global external HTTP(S) load balancer. A global forwarding rule sends the request to a target proxy, which checks the URL map and selects the backend service. The backend service sends the request to Compute Engine instance groups in multiple regions.

The request is received by the SSL proxy load balancer, which uses a global forwarding rule to check the URL map, then sends the request to a backend service. The request is processed by Compute Engine instance groups in multiple regions.

The request is matched by a URL map and then sent to a SSL proxy load balancer. A global forwarding rule sends the request to a target proxy, which selects a backend service and sends the request to Compute Engine instance groups in multiple regions.

The request is matched by a URL map and then sent to a global external HTTP(S) load balancer. A global forwarding rule sends the request to a target proxy, which selects a backend service. The backend service sends the request to Compute Engine instance groups in multiple regions.


8.
You have deployed your frontend web application in Kubernetes. Based on historical use, you need three pods to handle normal demand. Occasionally your load will roughly double. A load balancer is already in place. How could you configure your environment to efficiently meet that demand?

Edit your pod's configuration file and change the number of replicas to six.

Use the "kubectl autoscale" command to change the pod's maximum number of instances to six.

Use the "kubectl autoscale" command to change the deployment’s maximum number of instances to six.

Edit your deployment's configuration file and change the number of replicas to six.


9.
You are working with a client who has built a secure messaging application. The application is open source and consists of two components. The first component is a web app, written in Go, which is used to register an account and authorize the user’s IP address. The second is an encrypted chat protocol that uses TCP to talk to the backend chat servers running Debian. If the client's IP address doesn't match the registered IP address, the application is designed to terminate their session. The number of clients using the service varies greatly based on time of day, and the client wants to be able to easily scale as needed. What should you do?

Deploy the web application using the App Engine standard environment with a global external HTTP(S) load balancer and a network endpoint group. Use an unmanaged instance group for the backend chat servers. Use an external network load balancer to load-balance traffic across the backend chat servers.

Deploy the web application using the App Engine standard environment with a global external HTTP(S) load balancer and a network endpoint group. Use a managed instance group for the backend chat servers. Use a global SSL proxy load balancer to load-balance traffic across the backend chat servers.

Deploy the web application using the App Engine standard environment with a global external HTTP(S) load balancer and a network endpoint group. Use a managed instance group for the backend chat servers. Use an external network load balancer to load-balance traffic across the backend chat servers.

Deploy the web application using the App Engine flexible environment with a global external HTTP(S) load balancer and a network endpoint group. Use an unmanaged instance group for the backend chat servers. Use an external network load balancer to load-balance traffic across the backend chat servers.


10.
Cymbal Direct's user account management app allows users to delete their accounts whenever they like. Cymbal Direct also has a very generous 60-day return policy for users. The customer service team wants to make sure that they can still refund or replace items for a customer even if the customer’s account has been deleted. What can you do to ensure that the customer service team has access to relevant account information?

Temporarily disable the account for 30 days. Export account information to Cloud Storage, and enable lifecycle management to delete the data in 60 days.

Restore a previous copy of the user information database from a snapshot. Have a database administrator capture needed information about the customer.

Disable the account. Export account information to Cloud Storage. Have the customer service team permanently delete the data after 30 days.

Ensure that the user clearly understands that after they delete their account, all their information will also be deleted. Remind them to download a copy of their order history and account information before deleting their account. Have the support agent copy any open or recent orders to a shared spreadsheet.
