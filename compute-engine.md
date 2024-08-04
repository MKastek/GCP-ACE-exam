## Compute Engine  

- **Instance Groups**
    - An instance group is a set of virtual machine instances that you can collectively manage as a single entity.
        - Managed Instance Groups
            - Lets you operate apps on multiple identical VMs.
            - MIG is scalable and highly available.
            - It supports autoscaling, auto-healing, regional deployment, and automatic updating.
            - MIG can be set to perform auto-healing to keep your instances running at all times.
                - Activating this triggers health check to determine the status of instances and will try to recreate them when an instance is unhealthy.
- **Preemptible Instances**
    - A preemptible VM is an instance that you can provision at a much lower price point than normal instances.
    - Compute Engine might stop preemptible instances at any time due to system events.
    - This is perfect for fault-tolerant applications that can withstand possible instance preemption.
- Sole-tenant Nodes
    - A physical Compute Engine server dedicated exclusively for your use, these nodes are not shared with other users.


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

### Unmanaged Instance Groups in Compute Engine  
- Multiple possible heterogeneous VMs  
- Used to apply load balancing across heterogeneous group of instances  
- Recommended for legacy clusters  
- No autoscaling, autohealing, autoupdating  

### Managed Instance Groups in Compute Engine  
Managed instance groups are used to create sets of identically configured VMs that can autoscale an can be configure for regional deployment, they are resilient to a failure in a single zone.  
When configuring a managed instance group you should:  
- define health checks,
- provide number of instances.  

### Control in Compute Engine  
Compute Engine gives full control over operating system choice and configuration.  

### Guest attributes in Compute Engine     
When guest attributes are enabled, Compute Engine will store your generated host keys as guest attributes. SSH host keys on your VMs improve security.  

### Preemptible VM instances   
Preemptible VM instances on Google Compute Engine are short-lived compute instances that can be used at a much lower cost than regular instances. They are suitable for batch jobs and workloads that can tolerate interruptions because they may be shut down by Google at any time if their resources are needed elsewhere. However, since your jobs are running nightly and only take about 2 hours to complete, preemptible VMs are ideal as they are significantly cheaper and the likelihood of interruption is acceptable for batch jobs.


### Basic Rolling Update  
You can control various aspects of a rolling update, such as how many instances can be taken offline for the update, how long to wait between updating instances, whether the new template affects all or just a portion of instances, and so on.  


For advanced configurations, include other update options. If you don't specify otherwise, the `maxSurge` and `maxUnavailable` options default to 1 multiplied by the number of affected zones. This means that only 1 instance is taken offline in each affected zone, and the MIG creates only 1 additional instance per zone, during the update.  


Use the `maxSurge` option to configure how many new instances the MIG can create above its `targetSize` during an automated update. For example, if you set `maxSurge` to 5, the MIG uses the new instance template to create up to 5 new instances above your target size. Setting a higher maxSurge value speeds up your update, at the cost of additional instances.   

Use the `maxUnavailable` option to configure how many instances are unavailable at any time during an automated update. For example, if you set `maxUnavailable` to 5, then only 5 instances are taken offline for updating at a time. Use this option to control how disruptive the update is to your service and to control the rate at which the update is deployed.  
