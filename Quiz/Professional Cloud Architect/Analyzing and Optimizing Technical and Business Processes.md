1.
Your development team used Cloud Source Repositories, Cloud Build, and Artifact Registry to successfully implement the build portion of an application's CI/CD process.. However, the deployment process is erroring out. Initial troubleshooting shows that the runtime environment does not have access to the build images. You need to advise the team on how to resolve the issue. What could cause this problem?

-The runtime environment does not have permissions to Cloud Source Repositories in your current project.
_(Incorrect. Runtime environments do not need access to Cloud Source Repositories as part of the deployment process.)_

-The runtime environment does not have permissions to the Artifact Registry in your current project.
_(Incorrect. Runtime environments have read access permissions to Artifact Registry in the same project.)_

-You need to specify the Artifact Registry image by name.
_(Incorrect. In Artifact Registry, you need to identify images by tag or digest.)_

-The Artifact Registry might be in a different project.


2.
You have implemented a manual CI/CD process for the container services required for the next implementation of the Cymbal Direct’s Drone Delivery project. You want to automate the process. What should you do?

**-Implement a build trigger that applies your build configuration when a new software update is committed to Cloud Source Repositories.**
_(Correct! Configuring a build trigger automates the CI/CD process based on when the software is posted to a repository.)_

-Implement and reference a source repository in your Cloud Build configuration file.

-Configure and push a manifest file into an environment repository in Cloud Source Repositories.

-Specify the name of your Container Registry in your Cloud Build configuration.


3.
The number of requests received by your application is nearing the maximum specified in your design. You want to limit the number of incoming requests until the system can handle the workload. What design pattern does this situation describe?

-Applying exponential backoff
_(Incorrect. Exponential backoff increases the amount of time between retry requests. It does not limit them.)_

**-Applying a circuit breaker**
_(Correct! A circuit breaker limits requests based on a threshold that you specify.)_

-Applying graceful degradation

-Increasing jitter


4.
Developers on your team frequently write new versions of the code for one of your applications. You want to automate the build process when updates are pushed to Cloud Source Repositories. What should you do?

**-Implement a build trigger that references your repository and branch.**
_(Correct! Cloud Build triggers automate the build process when new files are placed into the name and branch of the repository that you specify.)_

-Implement a Cloud Build configuration file with build steps.

-Upload application updates and Cloud Build configuration files to Cloud Source Repositories.

-Set proper permissions for Cloud Build to access deployment resources.


5.
You want to establish procedures for testing the resilience of the delivery-by-drone solution. How would you simulate a scalability issue?

-Inject a bad health check for one or more of your resources.
_(Incorrect. Health checks help address availability needs.)_

-Block access to storage assets in one of your zones.
_(Incorrect. Ensuring that your data remains available in an outage is part of durability.)_

-Block access to all resources in a zone.
_(Incorrect. Responding to outages of zonal resources is a key capability in addressing availability.)_

-Load test your application to see how it responds.


6.
You have an application implemented on Compute Engine. You want to increase the durability of your application. What should you do?

-Implement a regional managed instance group.
_(Incorrect. Managed instance groups improve availability, not durability.)_

**-Implement a scheduled snapshot on your Compute Engine instances.**
_(Correct! Durability ensures that your data is protected and available. Snapshots are a viable way of backing up your data in Compute Engine.)_

-Perform health checks on your Compute Engine instances.

-Monitor your application’s usage metrics and implement autoscaling.


7.
The pilot subsystem in your Delivery by Drone service is critical to your service. You want to ensure that connections to the pilots can survive a VM outage without affecting connectivity. What should you do?

-Deploy a load balancer to distribute traffic across multiple machines.
_(Incorrect. Cloud Load Balancing helps distribute traffic across machines in multiple instance groups. It does not heal or scale VMs.)_

-Configure proper startup scripts for your VMs.
_(Incorrect. Startup scripts ensure that your machines are properly configured and ready to run your app. They do not help with outages.)_

**-Implement a managed instance group.**
_(Correct! Managed instance groups offer scaling and autohealing that automatically replaces the instances that are not responding.)_

-Create persistent disk snapshots.


8.
You are asked to implement a lift and shift operation for Cymbal Direct’s Social Media Highlighting service. You compose a Terraform configuration file to build all the necessary Google Cloud resources. What is the next step in the Terraform workflow for this effort?

-Run terraform plan to verify the contents of the Terraform configuration file.
_(Incorrect. You should run the init command before you run the plan command.)_

-Commit the configuration file to your software repository.
_(Incorrect. You should run init and run plan on your Terraform workflow before you commit the validated configuration file to your software repository.)_

**-Run terraform init to download the necessary provider modules.**
_(Correct! Running init in the directory containing your Terraform configuration file ensures that the correct plugins are loaded for the providers and resources requested.)_

-Run terraform apply to deploy the resources described in the configuration file.


9.
Cymbal Direct wants to improve its drone pilot interface. You want to collect feedback on proposed changes from the community of pilots before rolling out updates systemwide. What type of deployment pattern should you implement?

**-You should implement A/B testing.**
_(Correct! A/B testing is a pattern that lets you evaluate new proposed functionality.)_

-You should implement canary testing.

-You should implement an in-place release.

-You should implement a blue/green deployment.


10.
You are implementing a disaster recovery plan for the cloud version of your drone solution. Sending videos to the pilots is crucial from an operational perspective. What design pattern should you choose for this part of your architecture?

-Warm with a high recovery time objective (RTO)
_(Incorrect. A warm design pattern would consist of a standby system that you would fail over to if something went wrong. The RTO would be higher than with a hot design pattern.)_

**-Hot with a low recovery time objective (RTO)**
_(Correct! Safety and compliance require your application to have a low RTO, so you need a hot design pattern with minimal downtime.)_

-Hot with a high recovery time objective (RTO)

-Cold with a low recovery time objective (RTO)
