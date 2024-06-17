# GCP-ACE-exam

### Deployment Manager
This is a Google Cloud service that automates the creation and management of Google Cloud resources. Deployment Manager uses declarative configurations, where you can specify all the resources and their settings in a configuration file. This is ideal for scenarios where you have specific VM configurations that need to be consistently deployed and managed. It supports templates and parameterization, allowing for dynamic provisioning while adhering to defined specifications.


### Principle of least privilege
Give just enough permissions to perform the required tasks

### Remote Desktop Protocol
RDP uses port 3389, and without a proper firewall rule, you won't be able to connect to the instance.

### IAM users and roles assigned within a GCP 
The IAM section in the Google Cloud Console provides a comprehensive view of all IAM members (users, service accounts, groups, etc.) and their assigned roles within the selected project. It allows you to verify who has access to what resources within your project and with which permissions.

### Node Auto-Upgrades in GKE
This feature ensures that the nodes in your cluster are always up-to-date with the latest stable and supported version of Kubernetes. Google handles the upgrade process in a manner that aims to minimize downtime by carefully managing the upgrade of nodes. It is a key feature to maintain the reliability, security, and operational health of your applications. 

### DaemonSet 
A DaemonSet ensures that all (or some) Nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected.  
