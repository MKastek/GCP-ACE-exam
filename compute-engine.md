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
