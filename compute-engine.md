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

### Managed instance groups in Compute Engine  
Managed instance groups are used to create sets of identically configured VMs that can autoscale an can be configure for regional deployment, they are resilient to a failure in a single zone.  
When configuring a managed instance group you should:  
- define health checks,
- provide number of instances.  

### Control in Compute Engine  
Compute Engine gives full control over operating system choice and configuration.  

### Guest attributes in Compute Engine     
When guest attributes are enabled, Compute Engine will store your generated host keys as guest attributes. SSH host keys on your VMs improve security.  
