1.
Your client created an Identity and Access Management (IAM) resource hierarchy with Google Cloud when the company was a startup. Your client has grown and now has multiple departments and teams. You want to recommend a resource hierarchy that follows Google-recommended practices. What should you do?

-Use a flat resource hierarchy and multiple projects with established trust boundaries.

-Keep all resources in one project, and use a flat resource hierarchy to reduce complexity and simplify management.

-Keep all resources in one project, but change the resource hierarchy to reflect company organization.

-Use multiple projects with established trust boundaries, and change the resource hierarchy to reflect company organization.


2.
Michael is the owner/operator of “Zneeks,” a retail shoe store that caters to sneaker aficionados. He regularly works with customers who order small batches of custom shoes. Michael is interested in using Cymbal Direct to manufacture and ship custom batches of shoes to these customers. Reasonably tech-savvy but not a developer, Michael likes using Cymbal Direct's partner purchase portal but wants the process to be easy. What is an example of a user story that could describe Michael’s persona?

-Zneeks is a retail shoe store that caters to sneaker aficionados.

-As a shoe retailer, Michael wants to send Cymbal Direct custom purchase orders so that batches of custom shoes are sent to his customers.

-Michael is a tech-savvy owner/operator of a small business.

-Michael is reasonably tech-savvy but needs Cymbal Direct's partner purchase portal to be easy


3.
Cymbal Direct is experiencing success using Google Cloud and you want to leverage tools to make your solutions more efficient. Erik, one of the original web developers, currently adds new products to your application manually. Erik has many responsibilities and requires a long lead time to add new products. You need to create an App Engine application to let Cymbal Direct employees add new products instead of waiting for Erik. However, you want to make sure that only authorized employees can use the application. What should you do?

-Create a Google group and add authorized employees to it. Configure Identity-Aware Proxy (IAP) to the App Engine application as a HTTP-resource. Add the group as a principle with the role "Project Owner."

-Set up Cloud VPN between the corporate network and the Google Cloud project's VPC network. Allow users to connect to the App Engine instance.

-Use Google Cloud Armor to restrict access to the corporate network's external IP address. Configure firewall rules to allow only HTTP(S) access.

-Create a Google group and add authorized employees to it. Configure Identity-Aware Proxy (IAP) to the App Engine application as a HTTP-resource. Add the group as a principle with the role "IAP-secured Web App User."


4.
You've recently created an internal App Engine application for developers in your organization. The application lets developers clone production Cloud SQL databases into a project specifically created to test code and deployments. Your previous process was to export a database to a Cloud Storage bucket, and then import the SQL dump into a legacy on-premises testing environment database with connectivity to Google Cloud via Cloud VPN. Management wants to incentivize using the new process with Cloud SQL for rapid testing and track how frequently rapid testing occurs. How can you ensure that the developers use the new process?

-Use predefined roles to restrict access to what the developers are allowed to do. Create a group for the developers, and associate the group with the Cloud SQL Viewer role. Remove the "cloudsql.instances.export" ability from the role.

-Use an ACL on the Cloud Storage bucket. Create a read-only group that only has viewer privileges, and ensure that the developers are in that group.

-Leave the ACLs on the Cloud Storage bucket as-is. Disable Cloud VPN, and have developers use Identity-Aware Proxy (IAP) to connect. Create an organization policy to enforce public access protection.

-Create a custom role to restrict access to what developers are allowed to do. Create a group for the developers, and associate the group with your custom role. Ensure that the custom role does not have "cloudsql.instances.export."


5.
Cymbal Direct’s social media app must run in a separate project from its APIs and web store. You want to use Identity and Access Management (IAM) to ensure a secure environment. How should you set up IAM?

-Use separate service accounts for each component (social media app, APIs, and web store) with predefined or custom roles to grant access.

-Use separate service accounts for each component (social media app, APIs, and web store) with basic roles to grant access.

-Use one service account for each component (social media app, APIs, and web store) with basic roles to grant access.

-Use one service account for each component (social media app, APIs, and web store) with predefined or custom roles to grant access.


6.
Cymbal Direct wants to use Identity and Access Management (IAM) to allow employees to have access to Google Cloud resources and services based on their job roles. Several employees are project managers and want to have some level of access to see what has been deployed. The security team wants to ensure that securing the environment and managing resources is simple so that it will scale. What approach should you use?

-Give access directly to each individual for more granular control. Give access as low in the hierarchy as possible to prevent the inheritance of too many abilities from a higher level.

-Grant access by assigning custom roles to groups. Use multiple groups for better control. Give access as low in the hierarchy as possible to prevent the inheritance of too many abilities from a higher level.

-Grant access by assigning predefined roles to groups. Use multiple groups for better control. Give access as low in the hierarchy as possible to prevent the inheritance of too many abilities from a higher level.

-Grant access by assigning predefined roles to groups. Use multiple groups for better control. Make sure you give out access to all the children in a hierarchy under the level needed, because child resources will not automatically inherit abilities.


7.
Cymbal Direct has an application running on a Compute Engine instance. You need to give the application access to several Google Cloud services. You do not want to keep any credentials on the VM instance itself. What should you do?

-Create a service account for the instance. Use Access scopes to enable access to the required services.

-Create a service account for each of the services the VM needs to access. Associate the service accounts with the Compute Engine instance.

-Create a service account and assign it the project owner role, which enables access to any needed service.

-Create a service account with one or more predefined or custom roles, which give access to the required services.


8.
Cymbal Direct needs to make sure its new social media integration service can’t be accessed directly from the public internet. You want to allow access only through the web frontend store. How can you prevent access to the social media integration service from the outside world, but still allow access to the APIs of social media services?

-Limit access to the external IP addresses of the VM instances using a firewall rule to block all outbound traffic. Any SSH connection for management should be done with Identity-Aware Proxy (IAP) or a bastion host (jump box) after allowing SSH access from IAP or a corporate network.

-Remove external IP addresses from the VM instances running the social media service and place them in a private VPC behind Cloud NAT. Any SSH connection for management should be done with Identity-Aware Proxy (IAP) or a bastion host (jump box) after allowing SSH access from IAP or a corporate network.

-Limit access to the external IP addresses of the VM instances using firewall rules and place them in a private VPC behind Cloud NAT. Any SSH connection for management should be done with Identity-Aware Proxy (IAP) or a bastion host (jump box) after allowing SSH access from IAP or a corporate network.

-Remove external IP addresses from the VM instances running the social media service and place them in a private VPC behind Cloud NAT. Any SSH connection for management should be restricted to corporate network IP addresses by Google Cloud Armor.


9.
You have several Compute Engine instances running NGINX and Tomcat for a web application. In your web server logs, many login failures come from a single IP address, which looks like a brute force attack. How can you block this traffic?

-Ensure that an HTTP(S) load balancer is configured to send traffic to the backend Compute Engine instances running your web server. Create a Google Cloud Armor policy with a default rule action of "Allow." Add a new rule that specifies the IP address causing the login failures as the Condition, with an action of "Deny" and a deny status of "403," and accept the default priority (1000). Add the load balancer backend service's HTTP-backend as the target.

-Edit the Compute Engine instances running your web application, and enable Google Cloud Armor. Create a Google Cloud Armor policy with a default rule action of "Allow." Add a new rule that specifies the IP address causing the login failures as the Condition, with an action of "Deny” and a deny status of "403," and accept the default priority (1000).

-Ensure that an HTTP(S) load balancer is configured to send traffic to the backend Compute Engine instances running your web server. Create a Google Cloud Armor policy with a default rule action of "Deny." Add a new rule that specifies the IP address causing the login failures as the Condition, with an action of "Deny" and a deny status of "403," and accept the default priority (1000). Add the load balancer backend service's HTTP-backend as the target.

-Ensure that an HTTP(S) load balancer is configured to send traffic to your backend Compute Engine instances running your web server. Create a Google Cloud Armor policy using the instance’s local firewall with a default rule action of "Allow." Add a new local firewall rule that specifies the IP address causing the login failures as the Condition, with an action of "Deny" and a deny status of "403," and accept the default priority (1000).


10.
Your client is legally required to comply with the Payment Card Industry Data Security Standard (PCI-DSS). The client has formal audits already, but the audits are only done periodically. The client needs to monitor for common violations to meet those requirements more easily. The client does not want to replace audits but wants to engage in continuous compliance and catch violations early. What would you recommend that this client do?
Responses:

-Enable the Security Command Center (SCC) dashboard, asset discovery, and Security Health Analytics in the Premium tier. Export or view the PCI-DSS Report from the SCC dashboard's Vulnerabilities tab.

-Enable the Security Command Center (SCC) dashboard, asset discovery, and Security Health Analytics in the Premium tier. Export or view the PCI-DSS Report from the SCC dashboard's Compliance tab.

-Enable the Security Command Center (SCC) dashboard, asset discovery, and Security Health Analytics in the Standard tier. Export or view the PCI-DSS Report from the SCC dashboard's Compliance tab.

-Enable the Security Command Center (SCC) dashboard, asset discovery, and Security Health Analytics in the Standard tier. Export or view the PCI-DSS Report from the SCC dashboard's Vulnerabilities tab.
