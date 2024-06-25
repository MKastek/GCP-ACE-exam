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

### Kubernetes Logs  
Kubernetes Engine collects application logs by default when the log data is written to:  
- `STDOUT`  
- `STDERR`  

### Enable Cloud Operations  
Create clusters with parameter:  
`--logging`   
`--monitoring`  
  
### DaemonSet 
A DaemonSet ensures that all (or some) Nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected.  

### Cloud Spanner 
- Cloud Spanner is a fully managed, scalable, relational database service with global distribution and horizontal scaling capabilities.
- It's designed to handle large volumes of transactions and to scale horizontally across regions without significant downtime.
- Unlike some NoSQL databases that offer eventual consistency, Cloud Spanner provides strong consistency across global reads and writes, which is essential for relational data integrity.
- It requires minimal management from the user's end, handling most of the scaling aspects automatically

### Preemptible VM instances   
Preemptible VM instances on Google Compute Engine are short-lived compute instances that can be used at a much lower cost than regular instances. They are suitable for batch jobs and workloads that can tolerate interruptions because they may be shut down by Google at any time if their resources are needed elsewhere. However, since your jobs are running nightly and only take about 2 hours to complete, preemptible VMs are ideal as they are significantly cheaper and the likelihood of interruption is acceptable for batch jobs.

### Shared core machine type  
Shared core machine types offer a balance of performance and cost efficiency, making them a good choice for low-traffic, always-on applications.  

### Cloud Storage Object Lifecycle Management
- `Cloud Storage Object Lifecycle Management` allows you to define a set of rules that manage the lifecycle of your objects. The Age condition specifies the number of days since the object's creation.  
- The `SetStorageClass` action changes the storage class of objects within the bucket. Setting it to 90 days means that 90 days after the object's creation, it will be moved to Coldline Storage.  
- The Delete action specifies when the object should be deleted.

Change storage class:  
`gsutil rewrite -s Coldline gs://PATH_TO_OBJECT`  

Creation and content type of objects:  
`gsutil stat gs://BUCKET_NAME/OBJECT_NAME`  

### Nealine Storage 
Nearline Storage is a class of Cloud Storage designed for objects that will be accessed at most once every 30 days.  

### Coldline Storage
Coldline Storage is a storage class in Google Cloud Storage designed for data that you access less than once a quarter. It is priced lower than standard storage classes, making it cost-effective for long-term storage of data that is not accessed frequently.  

### Cloud Storage
Cloud Storage is designed to store large amounts of unstructured data in a variety of file formats, which makes it an ideal solution for storing data that will be used in ETL transformations. Data storage pricing is based on the amount of data and storage type. Standard storage is immediately available. Nearline storage is for data accessed roughly every 30 days. Egress is the amount of data read from the bucket and is also chargeable.   

### Change storage class  
`gcloud storage rewrite -s Coldline gs://PATH_TO_OBJECT`  

### Metada in Cloud Storage object  
`gsutil stat gs://BUCKET_NAME/OBJECT_NAME`  

### Cloud Storage Transfer  
Cloud Storage Transfer is a service provided by Google Cloud specifically designed for transferring large amounts of data between different cloud storage providers. For instance AWS S3 -> GCP bucker migration.  

### Access to Cloud Storage  
Access is granted to Cloud Storage objects using IAM or access control lists (ACLs). When `uniform bucket-level access` is applied, users only have access through IAM roles and permissions. A users that could access objects before uniform bucket-level access is applied but not after must have had access through ACLs.

### Shared VPC
Shared VPC allows projects to share a common VPC network. VPNs are used to link VPCs to on premises networks.

### Cloud Audit Logs
Google Cloud services write audit logs that record administrative activities and accesses within your Google Cloud resources. Audit logs help you answer "who did what, where, and when?"
Cloud Audit Logs maintain three audit logs:  
- `Admin Activity logs`,  
- `Data Access logs`,  
- `System Event logs`.

`Data Access Audit logs` generate large amounts of data and are disabled by default for most services; it is enabled by default for BigQuery. The other audit logs are not likely to generate the same volume of data as the Data Access Audit logs.    

### Target pools in Cloud Load Balancing
A target pool is a group of backend instances that receive incoming traffic from external passthrough Network Load Balancers. All backend instances of a target pool must reside in the same Google Cloud region. Target pools use HTTP health checks.

### URL maps in Cloud Load Balancing
URL maps specify direct requests to particular services. A URL map is a set of rules for routing incoming HTTP(S) requests to specific backend services or backend buckets. A minimal URL map matches all incoming request paths `/*`.

### Routes in Cloud Load Balancing
Routes are used to specify paths to destination IP addresses outside a subnet.

### Firewall rules in Cloud Load Balancing
Firewall rules control the flow of traffic on a network.  

### Traces in Cloud Load Balancing  
Traces are used to understand performance characteristics of services in a distributed system.  

### BigQuery
BigQuery is a managed, petabyte scale data warehouse, which uses SQL.  

### gcloud command to describe project
`gcloud projects describe <PROJECT_ID>`

### GKE default logs  
Kubernetes Engine collects log data written to standard output `STDOUT` and standard error `STDERR`.

### Clone persistent disk
The source and cloned disk must be in the _same zone_ and _region_ and must be of the _same type_. The size of the clone must be at least the size of the source disk but does not need to be the same. 

### App Engine  
App Engine is designed for applications written in supported languages, that need to run at low cost, and need to scale in response to rapid increases in load. App Engine is a managed service and as such minimizes operational overhead.

#### cron.yaml 
Cron.yaml files contain specifications for running scheduled jobs in App Engine.

#### app.yaml
App.yaml has overall application specifications.  

#### App Engine Standard  
App Engine Standard i a platform as a service (PaaS), you do not have to manage underlying infrastructure. It provides a secure sandbox environment for deploying new features quickly.  


### Datastore
#### index.yaml
Index.yaml files contain indexes for complex queries that reference more than one attribute. Datastore automatically creates indexes for single attributes. All queries must have a supporting index.  


### Cloud Dataproc  
Cloud Dataproc is a managed Spark/Hadoop service that can be used to migrate Hadoop clusters GCP.  

### Sole tenant node in Compute Engine  
On a sole tenant node in Compute Engine, only VMs from the same project will run on that node.  

### Cloud Identity  
Cloud Identity provides domain verification records, which are added to DNS settings for the domain.  

### Shielded VM in Compute Engine  
Shielded VMs are hardened virtual machines that use Secure Boot, virtual trusted platform module enabled Measured Boot, and integrity monitoring.  

### Image families in Compute Engine    
Image families are used to group related images together so you can roll forward or back between specific images versions. Image families always point to the latest version of an image that is not deprecated.  

### Instances template in Compute Engine  
Instance templates specify the configuration of virtual machines and managed instance groups.

### Managed instance groups in Compute Engine  
Managed instance groups are used to create sets of identically configured VMs that can autoscale an can be configure for regional deployment, they are resilient to a failure in a single zone.  
When configuring a managed instance group you should:  
- define health checks,
- provide number of instances.  

### Control in Compute Engine  
Compute Engine gives full control over operating system choice and configuration.  

### Guest attributes in Compute Engine     
When guest attributes are enabled, Compute Engine will store your generated host keys as guest attributes. SSH host keys on your VMs improve security.  

### Cloud Run  
Cloud Run is a managed compute platform that lets you run `containers` directly on top of Google's scalable infrastructure.
You can deploy code written in any programming language on Cloud Run if you can build a container image from it. In fact, building container images is optional.  

On Cloud Run, your code can either run continuously as a `service` or as a `job`. Both services and jobs run in the same environment and can use the same integrations with other services on Google Cloud.  


#### Environment variables for service  
When Cloud Run starts a container, it creates environment variables:  
- PORT  
- K_SERVICE  
- K_REVISION  
- K_CONFIGURATION  

K_Configuration specifies the configuration that created the container.
| Name|	Description |	Example |
| --- | ----------- | ---- |
| PORT|	The port your HTTP server should listen on. |	8080 |
| K_SERVICE |	The name of the Cloud Run service being run. |	hello-world |
| K_REVISION |	The name of the Cloud Run revision being run. |	hello-world.1 |
 K_CONFIGURATION |	The name of the Cloud Run configuration that created the revision. |	hello-world |  


 ### Cloud Foundation Toolkit
 #### Best-practice templates  
 The Cloud Foundation Toolkit provides a series of reference templates for Deployment Manager and Terraform which reflect Google Cloud best practices. These templates can be used off-the-shelf to quickly build a repeatable enterprise-ready foundation in Google Cloud. This frees you to focus on deploying your applications on this baseline secure environment. And with infrastructure as code (IaC), you can easily update the foundation as your needs change.  

 ### Transfer Appliance  
 Transfer Appliance is a high-capacity storage device that enables you to transfer and securely ship your data to a Google upload facility, where we upload your data to Cloud Storage.  

### Allocation quotas  
Allocation quotas, also known as resource quotas, define the number of resources that your project has access to. Compute Engine enforces allocation quotas on resource usage for various reasons. For example, quotas help to protect the community of Google Cloud users by preventing unforeseen spikes in usage.  

Allocation quotas are the maximum number of resources you can create of that resource type, if those resources are available. 

### Billing accounts in Google Cloud
-  Project and its resources can only be tied to one billing account.
-  Billing account can handle billing for more than one project.

### Project name
Project name is set by the user at creation. It does not have to be unique. It can be changed after creation time.  

### Network endpoint groups  
Network Endopint Group (NEG) is a configuration object that specifies a group of backend endpoints or services. Internal http(s) load balancer can only use NEGs.  

### Best practice for permissions  
- Minimize the number of individual resources you have to set permissions for.

### Use of service accounts in GKE  
When configuring access for GKE, you set up dedicated service accounts for each pod. You then use workload identity to map them to dedicated Kubernetes service accounts.

### Apigee API platform  
The Apigee API platform provides policy-based rate-limiting and routing services to help accommodate spikes in traffic. It also providdes OAuth 2.0 and SAML authentication.  

### Cloud Firestore  
Cloud Firestore is a mobile database service that can synchronize data between mobile devices and centralized storage.   

### Tunnels  
Tunnels are the network components that are configured to ensure traffic between VPN endpoints is encrypted. Tunnels create a secure, encrypted  connection between the endpoints, protecting the data being transmitted.   

### Identity in GCP  
An identity represents an entity such as a person or service account that can be granted privileges by assigning roles to the identity. Identity types include Google accounts, Cloud Identity or Google Workspace accounts, Google groups, and service accounts.
