1.
Which of these problems are containers intended to solve? Mark all that are correct (3 correct answers).

**A. Applications need a way to isolate their dependencies from one another.**
Correct.

**B. It's difficult to troubleshoot applications when they work on a developer's laptop but fail in production.**
Correct.

**C. Packaging applications in virtual machines can be wasteful.**
Correct.

D. Some developers need parts of their applications to be Linux-based while other parts are Windows-based.
_Feedback: Application components requiring different operating systems are not good candidates for containerization._


2.
You are choosing a technology for deploying applications, and you want to deliver them in lightweight, standalone, resource-efficient, portable packages. Which choice best meets those goals?

**A. Containers**
Correct.

B. Executable files
_Feedback: Review the Introduction to Containers lesson._

C. Hypervisors
_Feedback: Review the Introduction to Containers lesson._

D. Virtual Machines
_Feedback: Review the Introduction to Containers lesson._


3.
Why do Linux containers use union file systems?

A. To control an application's maximum consumption of CPU time and memory.
_Feedback: Linux cgroups provide this benefit._

B. To control what an application's ability to see parts of the directory tree and IP addresses.
_Feedback: Linux namespaces provide this benefit._

**C. To efficiently encapsulate applications and their dependencies into a set of clean, minimal layers.**
_Correct._

D. To give a container its own virtual memory address space.
_Feedback: Linux processes provide this benefit._


4.
What is significant about the topmost layer in a container? Choose all that are true (2 correct answers).

**A. An application running in a container can only modify the topmost layer.**
_Correct._

B. Reading from or writing to the topmost layer requires special privileges.
_Incorrect._

C. Reading from or writing to the topmost layer requires special software libraries.
_Incorrect._

**D. The topmost layer's contents are lost when the container is no longer running.**
_Correct._


5.
When you use Kubernetes, you describe the desired state you want, and Kubernetes's job is to make the deployed system conform to your desired state and to keep it there in spite of failures. What is the name for this management approach?

A. Containerization
_Incorrect._

**B. Declarative configuration**
_Correct._

C. Imperative configuration
_Incorrect._

D. Virtualization
_Incorrect._


6.
What is a stateful application?

A. An application that is not containerized.
_Incorrect._

**B. An application that requires data to be stored persistently.**
_Correct._

C. A web front end.
_Incorrect._


7.
You are classifying a number of your applications into workload types. Select the stateful applications in this list of applications. Choose all responses that are correct (2 correct responses).

**A. A gaming application that keeps track of user state persistently.**
_Correct._

**B. A shopping application that saves user shopping cart data between sessions.**
_Correct._

C. Image recognition application that identifies product defects from images.
_Feedback: Review the Introduction to Kubernetes lesson._

D. Web server front end for your inventory system.
_Feedback: Review the Introduction to Kubernetes lesson._


8.
What is the relationship between Kubernetes and Google Kubernetes Engine?

A. Google Kubernetes Engine is a closed-source variant of Kubernetes.
_Incorrect._

**B. Google Kubernetes Engine is Kubernetes as a managed service.**
_Correct._

C. Kubernetes and Google Kubernetes Engine are two names for the same thing.
_Incorrect._


9.
What is the name for the computers in a Kubernetes cluster that can run your workloads?

A. Containers
_Incorrect._

B. Container images
_Incorrect._

C. Control Planes
_Feedback: (In self-managed Kubernetes clusters, you can configure a control plane to also run your workloads in addition to its responsibilities as a control plane, but it's not the default, and this configuration is not possible in GKE.)

**D. Nodes**
_Correct._


10.
Which of the following supports scaling a Kubernetes cluster as a whole?

A. Compute Engine
_Feedback: Even though GKE uses Compute Engine to provide its resources, the capability to scale a cluster is provided by GKE itself. Attempting to scale a GKE cluster using Compute Engine tools would be an error._

**B. Google Kubernetes Engine**
_Correct._

C. Kubernetes
_Feedback: The capability to scale a Kubernetes cluster is provided by GKE._


11.
Google Compute Engine provides fine-grained control of costs. Which Compute Engine features provide this level of control?

A. Autoscaling groups
_Feedback: Review the Computing Options lesson._

B. Billing budgets and alerts
_Feedback: Review the Computing Options lesson._

**C. Fully customizable virtual machines**
_Correct._

D. Managed instance groups
_Feedback: Review the Computing Options lesson._

**E. Per-second billing**
_Correct._


12.
You are developing a new solution and want to explore serverless application solutions. Which Google Cloud compute services provide serverless compute resources that you can use with containers?

**A. App Engine**
_Correct._

B. Cloud Functions
_Feedback: Review the Computing Options lesson._

C. Compute Engine
_Feedback: Review the Computing Options lesson._

D. Google Kubernetes Engine
_Feedback: Review the Computing Options lesson._


13.
You are deploying a containerized application, and you want maximum control over how containers are configured and deployed. You want to avoid the operational management overhead of managing a full container cluster environment yourself. Which Google Cloud compute solution should you choose?

A. App Engine
_Feedback: Review the Computing Options lesson._

B. Cloud Functions
_Feedback: Review the Computing Options lesson._

C. Compute Engine
_Feedback: Review the Computing Options lesson._

**D. Google Kubernetes Engine**
_Correct._
