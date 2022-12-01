1.
Which control plane component does the kubectl command interact with?
A. etcd
_Feedback: Only kube-apiserver interacts with etcd._

B. kubelet
_Feedback: Only kube-apiserver interacts with the kubelets on the node._

**C. kube-apiserver**
_Correct._

D. The GKE API
_Feedback: kubectl is not aware of the GKE API._


2.
You want to use kubectl to configure your cluster, but first you must configure it. Where does the kubectl command store its configuration file?

A. kubectl always prompts the user for credentials before executing commands.
_Feedback: Review the lesson on the kubectl command._

B. kubectl uses the same authorization and credential tokens as the gcloud CLI utilities.
_Feedback: Review the lesson on the kubectl command._

C. The configuration information is stored in environment variables in the current shell when required.
_Feedback: Review the lesson on the kubectl command._

**D. The configuration information is stored in the $HOME/.kube/config file.**
_Correct._


3.
You want to use a kubectl get command to identify which Node each Pod is running on. Which command do you need to execute?

A. kubectl get nodes
_Feedback: Review the lesson on the kubectl command._

B. kubectl get nodes -o=yaml
_Feedback: Review the lesson on the kubectl command._

C. kubectl get pods
_Feedback: Review the lesson on the kubectl command._

**D. kubectl get pods -o=wide**
_Correct._

4.
What is the purpose of a Service? Choose all that are true (2 correct answers)

**A. To allow you to choose how Pods are exposed.**
_Correct._

B. To allow you to put constraints on Pods' resource consumption.
_Incorrect._

**C. To provide a load-balancing network endpoint for Pods.**
_Correct._

D. To provide a way to inspect and diagnose code running in a Pod.
_Incorrect._

5.
After a Deployment has been created and its component Pods are running, which component is responsible for ensuring that a replacement Pod is launched whenever a Pod fails or is evicted?

A. DaemonSet
_Feedback: Review the Deployments lesson._

B. Deployment
_Feedback: Review the Deployments lesson._

**C. ReplicaSet**
_Correct._

D. StatefulSet
_Feedback: Review the Deployments lesson._


6.
What is the relationship between Deployments and ReplicaSets?

**A. A Deployment configures a ReplicaSet controller to create and maintain a specific version of the Pods that the Deployment specifies.**
_Correct._

B. A Deployment configures a ReplicaSet controller to create and maintain all the Pods that the Deployment specifies, regardless of their version.
_Feedback: Review the lesson on Deployments._

C. A ReplicaSet configures a Deployment controller to create and maintain a specific version of the Pods that the Deployment specifies.
_Feedback: Review the lesson on Deployments._

D. There is no relationship; in modern Kubernetes, Replication Controllers are typically used to maintain a set of Pods in a running state.
_Feedback: Review the lesson on Deployments._


7.
What type of application is suited for use with a Deployment?

A. Batch
_Feedback: Review the lesson on Deployments._

B. Stateful
_Feedback: Review the lesson on Deployments._

**C. Stateless**
_Correct._

D. Written in Go
_Feedback: Kubernetes does not care what languages the applications it controls are written in._


8.
You have made a number of changes to your deployment and applied those changes. Which command should you use to rollback the environment to the deployment identified in the deployment history as revision 2?

A. Run ‘kubectl apply -f DEPLOYMENT_FILE --to-revision=2’
_Feedback: Review the lesson on Deployments._

B. Run ‘kubectl rollout undo deployment’ twice.
_Feedback: Review the lesson on Deployments._

**C. Run ‘kubectl rollout undo deployment --to-revision=2’**


D. Select the desired revision from the revision history list in the Cloud Console.
_Feedback: Review the lesson on Deployments._


9.
You are resolving a range of issues with a Deployment and need to make a large number of changes. Which command can you execute to group these changes into a single rollout, thus avoiding pushing out a large number of rollouts?

A. kubectl delete deployment
_Feedback: Review the lesson on Deployments._

**B. kubectl rollout pause deployment**
_Correct._

C. kubectl rollout resume deployment
_Feedback: Review the lesson on Deployments._

D. kubectl stop deployment
_Feedback: Review the lesson on Deployments._


10.
In GKE, what is the source of the IP addresses for Pods?

**A. Address ranges assigned to your Virtual Private Cloud**
_Correct._

B. Arbitrary network addresses per cluster
_Feedback: Review the lesson on Pod networking._

C. Loopback network addresses
_Feedback: Review the lesson on Pod networking._


11.
Your Pod has been rescheduled and the IP address that was assigned to the Pod when it was originally scheduled is no longer accessible. What is the reason for this?

A. The new Pod IP address is blocked by a firewall.
_Feedback: Review the lesson on Pod networking._

**B. The new Pod has received a different IP address.**
_Correct._

C. The old Pod IP address is blocked by a firewall.
_Feedback: Review the lesson on Pod networking._

D. The Pod IP range for the cluster is exhausted.
_Feedback: Review the lesson on Pod networking._


12.
What happens if a Pod fails while it is using a persistent volume?

A. The volumes are deleted, and their contents are lost.
_Feedback: Review the lesson on volumes._

B. The volumes are unmounted from the failing Pod, and their contents are deleted.
_Feedback: Review the lesson on volumes._

C. The volumes are unmounted from the failing Pod, and their contents revert to what they had before the Pod was attached to it.
_Feedback: Review the lesson on volumes._

**D. The volumes are unmounted from the failing Pod, and they continue to exist with their last contents.**
_Correct._


13.
How can a Pod request persistent storage without specifying the details of how that storage is to be implemented?

A. By using a gcePersistentDisk
_Feedback: Review the video on PersistentVolumes and PersistentVolumeClaims._

B. By using a PersistentVolume
_Feedback: Review the video on PersistentVolumes and PersistentVolumeClaims._

**C. By using a PersistentVolumeClaim**
_Correct._

D. By using an emptyDir
_Feedback: Review the video on PersistentVolumes and PersistentVolumeClaims._


14.
An application owner has created a Pod manifest using a PersistentVolumeClaim with a StorageClassName value of standard. What type of storage is used for this volume in a GKE Cluster?

**A. Google Persistent Disk**
_Correct._

B. Local volume on the node
_Feedback: Review the lesson on Kubernetes Volumes._

C. Memory Backed
_Feedback: Review the lesson on Kubernetes Volumes._

D. NFS Storage
_Feedback: Review the lesson on Kubernetes Volumes._
