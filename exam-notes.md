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



### Enable Cloud Operations  
Create clusters with parameter:  
`--logging`   
`--monitoring`  
  
### Cloud Spanner 
- Cloud Spanner is a fully managed, scalable, relational database service with global distribution and horizontal scaling capabilities.
- It's designed to handle large volumes of transactions and to scale horizontally across regions without significant downtime.
- Unlike some NoSQL databases that offer eventual consistency, Cloud Spanner provides strong consistency across global reads and writes, which is essential for relational data integrity.
- It requires minimal management from the user's end, handling most of the scaling aspects automatically

### Shared core machine type  
Shared core machine types offer a balance of performance and cost efficiency, making them a good choice for low-traffic, always-on applications.  
 

### Cloud Audit Logs
Google Cloud services write audit logs that record administrative activities and accesses within your Google Cloud resources. Audit logs help you answer "who did what, where, and when?"
Cloud Audit Logs maintain three audit logs:  
- `Admin Activity logs`,  
- `Data Access logs`,  
- `System Event logs`.

`Data Access Audit logs` generate large amounts of data and are disabled by default for most services; it is enabled by default for BigQuery. The other audit logs are not likely to generate the same volume of data as the Data Access Audit logs.    


### Clone persistent disk
The source and cloned disk must be in the _same zone_ and _region_ and must be of the _same type_. The size of the clone must be at least the size of the source disk but does not need to be the same. 



### Datastore
#### index.yaml
Index.yaml files contain indexes for complex queries that reference more than one attribute. Datastore automatically creates indexes for single attributes. All queries must have a supporting index.  


### Cloud Dataproc  
Cloud Dataproc is a managed Spark/Hadoop service that can be used to migrate Hadoop clusters GCP.  


 ### Cloud Foundation Toolkit
 #### Best-practice templates  
 The Cloud Foundation Toolkit provides a series of reference templates for Deployment Manager and Terraform which reflect Google Cloud best practices. These templates can be used off-the-shelf to quickly build a repeatable enterprise-ready foundation in Google Cloud. This frees you to focus on deploying your applications on this baseline secure environment. And with infrastructure as code (IaC), you can easily update the foundation as your needs change.  

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
 

### Make VM to use specific service account instead of the default Compute Engine service account  
When creating the VM via the web console, specify the service account under the 'Identity and API Access' section.  




