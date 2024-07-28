# GCP-ACE-exam

### Deployment Manager
This is a Google Cloud service that automates the creation and management of Google Cloud resources. Deployment Manager uses declarative configurations, where you can specify all the resources and their settings in a configuration file. This is ideal for scenarios where you have specific VM configurations that need to be consistently deployed and managed. It supports templates and parameterization, allowing for dynamic provisioning while adhering to defined specifications.  

Deployment Manager is a configuration management tool that allows you to define and deploy a set of resources, including Compute Engine VMs, in a declarative manner. You can use it to specify the exact specifications of your VMs in a configuration file, and Deployment Manager will create and manage those VMs for you. Deployment Manager is recommended by Google as a way to automate and manage the deployment of resources on the Google Cloud Platform.

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

### Shared core machine type  
Shared core machine types offer a balance of performance and cost efficiency, making them a good choice for low-traffic, always-on applications.  


### Cloud Storage Transfer  
Cloud Storage Transfer is a service provided by Google Cloud specifically designed for transferring large amounts of data between different cloud storage providers. For instance AWS S3 -> GCP bucker migration.  


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

### Cloud SQL - Point-in-time-recovery (PITR)  
Point-in-time recovery (PITR) helps you recover an instance to a specific point in time. For example, if an error causes a loss of data, you can recover a database to its state before the error occurred.

`PITR` always creates a new instance; you can't perform a PITR to an existing instance. The new instance inherits the settings of the source instance, similar to how clone creation works. However, for the new instance to inherit these settings, the instance's state must be `RUNNABLE`.  

When you create a Cloud SQL instance in the Google Cloud console, PITR is enabled by default.  
`PITR` uses binary logging to archive logs.  

### Give access to VMs in Compute Engine  
 Generate a new SSH key pair. Give the private key to each member of your team. Configure the public key as a project-wide public SSH key in your Cloud Platform project and allow project-wide public SSH keys on each instance.  

 ### Backup for distater recovery  
 Use GCP Cloud Storage for distater recovery, use Coldline Storage for low costs.  

 ### gcloud iam roles copy  
 gcloud iam roles copy - create a role from an existing role  
```
gcloud iam roles copy [--dest-organization=DEST_ORGANIZATION] [--dest-project=DEST_PROJECT]
[--destination=DESTINATION] [--source=SOURCE] [--source-organization=SOURCE_ORGANIZATION]  
[--source-project=SOURCE_PROJECT]  
```


### Bigquery dry run
BigQuery provides various methods to estimate cost:  
- Use the query dry run option to estimate costs before running a query using the on-demand pricing model.  
- Calculate the number of bytes processed by various types of query.  
- Get the monthly cost based on projected usage by using the Google Cloud Pricing Calculator.

A dry run in BigQuery provides the following information:  
- estimate of charges in on-demand mode  
- validation of your query  
- approximate size and complexity of your query in capacity mode

### How to use dry run - you want to find out how much it will cost to run the query  
Use the command line to run a dry run query to estimate the number of bytes read. Then convert that bytes estimate to dollars using the Pricing Calculator.  

### Make VM to use specific service account instead of the default Compute Engine service account  
When creating the VM via the web console, specify the service account under the 'Identity and API Access' section.  




