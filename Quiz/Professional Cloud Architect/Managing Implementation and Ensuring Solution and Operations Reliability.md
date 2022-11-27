1.

You are using Cloud Run to deploy a Flask web application named app.py written in Python. In your testing and staging environments, the application performed as expected. When the application was deployed to production, product search results displayed products that should have been filtered out based on the user's preferences. The developer believes this performance issue would result from the 'user.productFilter' variable either not being set or not being evaluated correctly. You want visibility into what is happening, but also want to minimize user impact, because this is not a critical bug. What should you do?

Use ssh to connect to the Compute Engine instance where Cloud Run is running. Use the command 'pip install google-python-cloud-debugger' to install Cloud Debugger. Use the 'gcloud debug' command to debug the application.

Modify the Dockerfile for the Cloud Run application. Change the RUN command to 'python3 -m pdb /app.py'. Modify the script to import pdb. Deploy to Cloud Run as a canary build.

Use ssh to connect to the Compute Engine instance where Cloud Run is running. Run the command 'python3 -m pdb app.py' to debug the application.

Modify the Dockerfile for the Cloud Run application. Add 'RUN 'pip install google-python-cloud-debugger' to the Dockerfile. Modify the script to import googleclouddebugger. Use 'gcloud debug' to debug the application.
2.

Cymbal Direct’s warehouse and inventory system was written in Java. The system uses a microservices architecture in GKE and is instrumented with Zipkin. Seemingly at random, a request will be 5-10 times slower than others. The development team tried to reproduce the problem in testing, but failed to determine the cause of the issue. What should you do?

Create metrics in Cloud Monitoring for your microservices to test whether they are intermittently unavailable or slow to respond to HTTPS requests. Use Cloud Trace to determine which functions/methods in your application’s code use the most system resources. Use Cloud Profiler to identify slow requests and determine which microservices/calls take the most time to respond.

Use Error Reporting to test whether your microservices are intermittently unavailable or slow to respond to HTTPS requests. Use Cloud Profiler to determine which functions/methods in your application’s code use the most system resources. Use Cloud Trace to identify slow requests and determine which microservices/calls take the most time to respond.

Create metrics in Cloud Monitoring for your microservices to test whether they are intermittently unavailable or slow to respond to HTTPS requests. Use Cloud Profiler to determine which functions/methods in your application’s code use the most system resources. Use Cloud Trace to identify slow requests and determine which microservices/calls take the most time to respond.

Use Error Reporting to test whether your microservices are intermittently unavailable or slow to respond to HTTPS requests. Use Cloud Trace to determine which functions/methods in your application’s code Use the most system resources. Use Cloud Profiler to identify slow requests and determine which microservices/calls take the most time to respond.
3.

Your organization is planning a disaster recovery (DR) strategy. Your stakeholders require a recovery time objective (RTO) of 0 and a recovery point objective (RPO) of 0 for zone outage. They require an RTO of 4 hours and an RPO of 1 hour for a regional outage. Your application consists of a web application and a backend MySQL database. You need the most efficient solution to meet your recovery KPIs. What should you do?

Use a global HTTP(S) load balancer. Deploy the web application as Compute Engine managed instance groups (MIG) in two regions, us-west and us-east. Configure the load balancer to the us-east backend. Use Cloud SQL with high availability (HA) enabled in us-east and a cross-region replica in us-west. Manually promote the us-west Cloud SQL instance and change the load balancer backend to us-west.

Use a global HTTP(S) load balancer. Deploy the web application as Compute Engine managed instance groups (MIG) in two regions, us-west and us-east. Configure the load balancer to use both backends. Use Cloud SQL with high availability (HA) enabled in us-east and back up the database every hour to a multi-region Cloud Storage bucket. Restore the data to a Cloud SQL database in us-west if there is a failure.

Use a global HTTP(S) load balancer. Deploy the web application as Compute Engine managed instance groups (MIG) in two regions, us-west and us-east. Configure the load balancer to use both backends. Use Cloud SQL with high availability (HA) enabled in us-east and a cross-region replica in us-west.

Use a global HTTP(S) load balancer. Deploy the web application as Compute Engine managed instance groups (MIG) in two regions, us-west and us-east. Configure the load balancer to use both backends. Use Cloud SQL with high availability (HA) enabled in us-east and back up the database every hour to a multi-region Cloud Storage bucket. Restore the data to a Cloud SQL database in us-west if there is a failure and change the load balancer backend to us-west.
4.

You need to adopt Site Reliability Engineering principles and increase visibility into your environment. You want to minimize management overhead and reduce noise generated by the information being collected. You also want to streamline the process of reacting to analyzing and improving your environment, and to ensure that only trusted container images are deployed to production. What should you do?

Adopt Google Cloud’s operations suite to gain visibility into the environment. Use Cloud Trace for distributed tracing, Cloud Logging for logging, and Cloud Monitoring for monitoring, alerting, and dashboards. Page the on-call contact when issues that affect resources in the environment are detected. Use GPG to check container image signatures and ensure that only signed containers are deployed.

Adopt Google Cloud’s operations suite to gain visibility into the environment. Use Cloud Trace for distributed tracing, Cloud Logging for logging, and Cloud Monitoring for monitoring, alerting, and dashboards. Only page the on-call contact about novel issues or events that haven’t been seen before. Use Binary Authorization to ensure that only signed container images are deployed.

Adopt Google Cloud’s operations suite to gain visibility into the environment. Use Cloud Trace for distributed tracing, Cloud Logging for logging, and Cloud Monitoring for monitoring, alerting, and dashboards. Only page the on-call contact about novel issues or events that haven’t been seen before. Use GNU Privacy Guard (GPG) to check container image signatures and ensure that only signed containers are deployed.

Adopt Google Cloud’s operations suite to gain visibility into the environment. Use Cloud Trace for distributed tracing, Cloud Logging for logging, and Cloud Monitoring for monitoring, alerting, and dashboards. Page the on-call contact when issues that affect resources in the environment are detected. Use Binary Authorization to ensure that only signed container images are deployed.
5.

Your client has adopted a multi-cloud strategy that uses a virtual machine-based infrastructure. The client's website serves users across the globe. The client needs a single dashboard view to monitor performance in their AWS and Google Cloud environments. Your client previously experienced an extended outage and wants to establish a monthly service level objective (SLO) of no outage longer than an hour. What should you do?

In Cloud Monitoring, create an uptime check for the URL your clients will access. Configure it to check from multiple regions. Use the Cloud Monitoring dashboard to view the uptime metrics over time and ensure that the SLO is met. Recommend an SLO of 97% uptime per day.

Authorize access to your Google Cloud project from AWS with a service account. Install the monitoring agent on AWS EC2 (virtual machines) and Compute Engine instances. Use Cloud Monitoring to create dashboards that use the performance metrics from virtual machines to ensure that the SLO is met.

In Cloud Monitoring, create an uptime check for the URL your clients will access. Configure it to check from multiple regions. Use the Cloud Monitoring dashboard to view the uptime metrics over time and ensure that the SLO is met. Recommend an SLO of 97% uptime per month.

Create a new project to use as an AWS connector project. Authorize access to the project from AWS with a service account. Install the monitoring agent on AWS EC2 (virtual machines) and Compute Engine instances. Use Cloud Monitoring to create dashboards that use the performance metrics from virtual machines to ensure that the SLO is met.
6.

Cymbal Direct uses a proprietary service to manage on-call rotation and alerting. The on-call rotation service has an API for integration. Cymbal Direct wants to monitor its environment for service availability and ensure that the correct person is notified. What should you do?

Ensure that VPC firewall rules allow access from the IP addresses used by Google Cloud's uptime-check servers. Create a Pub/Sub topic for alerting as a monitoring notification channel in Google Cloud’s operations suite. Create an uptime check for the appropriate resource's external IP address, with an alerting policy set to use the Pub/Sub topic. Create a Cloud Function that subscribes to the Pub/Sub topic to send the alert to the on-call API.

Ensure that VPC firewall rules allow access from the on-call API. Create a Cloud Function to send the alert to the on-call API. Add Cloud Functions as a monitoring notification channel in Google Cloud’s operations suite. Create an uptime check for the appropriate resource's external IP address, with an alerting policy set to use the Cloud Function.

Ensure that VPC firewall rules allow access from the IP addresses used by Google Cloud’s uptime-check servers. Create a Pub/Sub topic for alerting as a monitoring notification channel in Google Cloud’s operations suite. Create an uptime check for the appropriate resource's internal IP address, with an alerting policy set to use the Pub/Sub topic. Create a Cloud Function that subscribes to the Pub/Sub topic to send the alert to the on-call API.

Ensure that VPC firewall rules allow access from the IP addresses used by Google Cloud's uptime-check servers. Add the URL for the on-call rotation API as a monitoring notification channel in Google Cloud’s operations suite. Create an uptime check for the appropriate resource's internal IP address, with an alerting policy set to use the API.
7.

Cymbal Direct is working on a social media integration service in Google Cloud. Mahesh is a non-technical manager who wants to ensure that the project doesn’t exceed the budget and responds quickly to unexpected cost increases. You need to set up access and billing for the project. What should you do?
Responses:


Assign the predefined Billing Account Administrator role to Mahesh. Create a project budget. Configure billing alerts to be sent to the Project Owner. Use resource quotas to cap how much money can be spent.

Use the predefined Billing Account Administrator role for the Billing Administrator group, and assign Mahesh to the group. Create a project budget. Configure billing alerts to be sent to the Billing Administrator. Use resource quotas to cap how many resources can be deployed.

Assign the predefined Billing Account Administrator role to Mahesh. Create a project budget. Configure billing alerts to be sent to the Billing Administrator. Use resource quotas to cap how many resources can be deployed.

Use the predefined Billing Account Administrator role for the Billing Administrator group, and assign Mahesh to the group. Create a project budget. Configure billing alerts to be sent to the Billing Account Administrator. Use resource quotas to cap how much money can be spent.
8.

Cymbal Direct has a new social media integration service that pulls images of its products from social media sites and displays them in a gallery of customer images on your online store. You receive an alert from Cloud Monitoring at 3:34 AM on Saturday. The store is still online, but the gallery does not appear. The CPU utilization is 30% higher than expected on the VMs running the service, which causes the managed instance group (MIG) to scale to the maximum number of instances. You verify that the issue is real by checking the site, and verify that it is not CPU-related by checking the incidents timeline. What should you do to resolve the issue?

Check the incident documentation or labels to determine the on-call contact. Appoint an incident commander, and open a chat channel, or conference call for emergency response. Investigate and resolve the issue by increasing the maximum number of instances in the MIG, and verify that this resolves the issue. Mark the incident as closed.

Increase the maximum number of instances in the MIG and verify that this resolves the issue. Check the incident documentation or labels to determine the on-call contact. Appoint an incident commander, and open a chat channel, or conference call for emergency response. Investigate and resolve the root cause of the issue. Write a blameless post-mortem and identify steps to prevent the issue, to ensure a culture of continuous improvement.

Increase the maximum number of instances in the MIG and verify that this resolves the issue. Ensure that the ticket is annotated with your solution. Create a normal work ticket for the application developer with a link to the incident. Mark the incident as closed.

Increase the maximum number of instances in the MIG and verify that this resolves the issue.
9.

Cymbal Direct releases new versions of its drone delivery software every 1.5 to 2 months. Although most releases are successful, you have experienced three problematic releases that made drone delivery unavailable while software developers rolled back the release. You want to increase the reliability of software releases and prevent similar problems in the future. What should you do?

Adopt a “waterfall” development process. Maintain the current release schedule. Ensure that documentation explains how all the features interact. Automate testing of the application. Ensure that the process to roll back the release is well documented. Use Cloud Monitoring, Cloud Logging, and Cloud Alerting to ensure visibility.

Adopt an “agile” development process. Maintain the current release schedule. Automate build processes from a source repository. Automate testing after the build process. Use Cloud Monitoring, Cloud Logging, and Cloud Alerting to ensure visibility. Deploy the previous version if problems are detected and you need to roll back.

Adopt a “waterfall” development process. Maintain the current release schedule. Ensure that documentation explains how all the features interact. Ensure that the entire application is tested in a staging environment before the release. Ensure that the process to roll back the release is documented. Use Cloud Monitoring, Cloud Logging, and Cloud Alerting to ensure visibility.

Adopt an “agile” development process. Reduce the time between releases as much as possible. Automate the build process from a source repository, which includes versioning and self-testing. Use Cloud Monitoring, Cloud Logging, and Cloud Alerting to ensure visibility. Use a canary deployment to detect issues that could cause rollback.
10.

Your environment has multiple projects used for development and testing. Each project has a budget, and each developer has a budget. A personal budget overrun can cause a project budget overrun. Several developers are creating resources for testing as part of their CI/CD pipeline but are not deleting these resources after their tests are complete. If the compute resource fails during testing, the test can be run again. You want to reduce costs and notify the developer when a personal budget overrun causes a project budget overrun. What should you do?

Configure billing export to BigQuery. Create a Google Cloud budget for each project. Configure a billing alert to notify billing admins and users when their budget is exceeded. Modify the build scripts/pipeline to label all resources with the label “creator” set to the developer’s email address. Use spot (preemptible) instances wherever possible.

Configure billing export to BigQuery. Create a Google Cloud budget for each project. Create a Pub/Sub topic for developer-budget-notifications. Create a Cloud Function to notify the developer based on the labels. Modify the build scripts/pipeline to label all resources with the label “creator” set to the developer’s email address. Use spot (preemptible) instances wherever possible.

Configure billing export to BigQuery. Create a Google Cloud budget for each project. Create a group for the developers in each project, and add them to the appropriate group. Create a notification channel for each group. Configure a billing alert to notify the group when their budget is exceeded. Modify the build scripts/pipeline to label all resources with the label “creator” set to the developer’s email address. Use spot (preemptible) instances wherever possible.

Configure billing export to BigQuery. Create a Google Cloud budget for each project. Create a Pub/Sub topic for developer-budget-notifications. Create a Cloud Function to notify the developer based on the labels. Modify the build scripts/pipeline to label all resources with the label “creator” set to the developer’s email address. Use spot (preemptible) instances wherever possible. Use Cloud Scheduler to delete resources older than 24 hours in each project.
