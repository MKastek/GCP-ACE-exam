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

### Cloud Spanner 
- Cloud Spanner is a fully managed, scalable, relational database service with global distribution and horizontal scaling capabilities.
- It's designed to handle large volumes of transactions and to scale horizontally across regions without significant downtime.
- Unlike some NoSQL databases that offer eventual consistency, Cloud Spanner provides strong consistency across global reads and writes, which is essential for relational data integrity.
- It requires minimal management from the user's end, handling most of the scaling aspects automatically

### Preemptible VM instances   
Preemptible VM instances on Google Compute Engine are short-lived compute instances that can be used at a much lower cost than regular instances. They are suitable for batch jobs and workloads that can tolerate interruptions because they may be shut down by Google at any time if their resources are needed elsewhere. However, since your jobs are running nightly and only take about 2 hours to complete, preemptible VMs are ideal as they are significantly cheaper and the likelihood of interruption is acceptable for batch jobs.

### Cloud Storage Object Lifecycle Management
- `Cloud Storage Object Lifecycle Management` allows you to define a set of rules that manage the lifecycle of your objects. The Age condition specifies the number of days since the object's creation.  
- The `SetStorageClass` action changes the storage class of objects within the bucket. Setting it to 90 days means that 90 days after the object's creation, it will be moved to Coldline Storage.  
- The Delete action specifies when the object should be deleted.

### Nealine Storage 
Nearline Storage is a class of Cloud Storage designed for objects that will be accessed at most once every 30 days.  

### Coldline Storage
Coldline Storage is a storage class in Google Cloud Storage designed for data that you access less than once a quarter. It is priced lower than standard storage classes, making it cost-effective for long-term storage of data that is not accessed frequently.  

### Cloud Storage
Cloud Storage is designed to store large amounts of unstructured data in a variety of file formats, which makes it an ideal solution for storing data that will be used in ETL transformations.

### Shared VPC
Shared VPC allows projects to share a common VPC network. VPNs are used to link VPCs to on premises networks.

### Cloud Audit Logs
Google Cloud services write audit logs that record administrative activities and accesses within your Google Cloud resources. Audit logs help you answer "who did what, where, and when?"
Cloud Audit Logs maintain three audit logs:  
- `Admin Activity logs`,  
- `Data Access logs`,  
- `System Event logs`.  

### Target pools in Cloud Load Balancing
A target pool is a group of backend instances that receive incoming traffic from external passthrough Network Load Balancers. All backend instances of a target pool must reside in the same Google Cloud region. Target pools use HTTP health checks.


### BigQuery
BigQuery is a managed, petabyte scale data warehouse, which uses SQL.  

### gcloud command to describe project
`gcloud projects describe <PROJECT_ID>`

### GKE default logs  
Kubernetes Engine collects log data written to standard output `STDOUT` and standard error `STDERR`.

### Clone persistent disk
The source and cloned disk must be in the _same zone_ and _region_ and must be of the _same type_. The size of the clone must be at least the size of the source disk but does not need to be the same. 
