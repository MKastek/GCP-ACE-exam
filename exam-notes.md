# GCP-ACE-exam

### Deployment Manager
This is a Google Cloud service that automates the creation and management of Google Cloud resources. Deployment Manager uses declarative configurations, where you can specify all the resources and their settings in a configuration file. This is ideal for scenarios where you have specific VM configurations that need to be consistently deployed and managed. It supports templates and parameterization, allowing for dynamic provisioning while adhering to defined specifications.  

Deployment Manager is a configuration management tool that allows you to define and deploy a set of resources, including Compute Engine VMs, in a declarative manner. You can use it to specify the exact specifications of your VMs in a configuration file, and Deployment Manager will create and manage those VMs for you. Deployment Manager is recommended by Google as a way to automate and manage the deployment of resources on the Google Cloud Platform.


### Remote Desktop Protocol
RDP uses port 3389, and without a proper firewall rule, you won't be able to connect to the instance.




### Enable Cloud Operations  
Create clusters with parameter:  
`--logging`   
`--monitoring`  
  
### Cloud Spanner 
- Cloud Spanner is a fully managed, scalable, relational database service with global distribution and horizontal scaling capabilities.
- It's designed to handle large volumes of transactions and to scale horizontally across regions without significant downtime.
- Unlike some NoSQL databases that offer eventual consistency, Cloud Spanner provides strong consistency across global reads and writes, which is essential for relational data integrity.
- It requires minimal management from the user's end, handling most of the scaling aspects automatically

 

### Cloud Audit Logs
Google Cloud services write audit logs that record administrative activities and accesses within your Google Cloud resources. Audit logs help you answer "who did what, where, and when?"
Cloud Audit Logs maintain three audit logs:  
- `Admin Activity logs`,  
- `Data Access logs`,  
- `System Event logs`.

`Data Access Audit logs` generate large amounts of data and are disabled by default for most services; it is enabled by default for BigQuery. The other audit logs are not likely to generate the same volume of data as the Data Access Audit logs.    


### Clone persistent disk
The source and cloned disk must be in the _same zone_ and _region_ and must be of the _same type_. The size of the clone must be at least the size of the source disk but does not need to be the same. 



### Cloud Dataproc  
Cloud Dataproc is a managed Spark/Hadoop service that can be used to migrate Hadoop clusters GCP.  


 ### Cloud Foundation Toolkit
 #### Best-practice templates  
 The Cloud Foundation Toolkit provides a series of reference templates for Deployment Manager and Terraform which reflect Google Cloud best practices. These templates can be used off-the-shelf to quickly build a repeatable enterprise-ready foundation in Google Cloud. This frees you to focus on deploying your applications on this baseline secure environment. And with infrastructure as code (IaC), you can easily update the foundation as your needs change.  


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
   

### Tunnels  
Tunnels are the network components that are configured to ensure traffic between VPN endpoints is encrypted. Tunnels create a secure, encrypted  connection between the endpoints, protecting the data being transmitted.   

### Identity in GCP  
An identity represents an entity such as a person or service account that can be granted privileges by assigning roles to the identity. Identity types include Google accounts, Cloud Identity or Google Workspace accounts, Google groups, and service accounts.  


### Give access to VMs in Compute Engine  
 Generate a new SSH key pair. Give the private key to each member of your team. Configure the public key as a project-wide public SSH key in your Cloud Platform project and allow project-wide public SSH keys on each instance.  

 ### Backup for distater recovery  
 Use GCP Cloud Storage for distater recovery, use Coldline Storage for low costs.  

 

### Make VM to use specific service account instead of the default Compute Engine service account  
When creating the VM via the web console, specify the service account under the 'Identity and API Access' section.  




