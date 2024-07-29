## Kubernetes

- **Features**
    - Can be configured to automatically scale node pool and clusters across multiple node pools based on changing workload requirements.
    - Auto-repair can be enabled to do health checks on node.
    - Can enable Cloud Logging and Cloud Monitoring via simple checkbox configurations.
    - Kubernetes version can be enabled to auto-upgrade with the latest release patch.
    - Supports Docker container format.
    - Integrates with Google Container Registry so you can easily access your private Docker images.
- **kubectl**
    - The main CLI tool for running commands and managing Kubernetes clusters
- **Cluster**
    - All of the Kubernetes objects that represent your containerized applications run on top of a cluster.
- **Node**
    - Nodes are the worker machines that run your containerized applications and other workloads.
    - A cluster typically has one or more *nodes.*
    - Kubernetes runs your workload by placing containers into pods to run on nodes.
- **Node Pool**
    - A node pool is a set of nodes within a cluster that have similar configurations.
- **Cluster Autoscaler**
    - Cluster Autoscaler automatically resizes the number of nodes in a given node pool, based on the demands of your workloads.
- **Kubernetes API Objects**
    - Pods
        - Are the smallest deployable units of computing that you can create and manage in Kubernetes.
        - Every pod has its own IP address.
    - Deployment
        - You described the desired state in a *deployment*, and the Deployment Controller changes the actual state to the desired state at a controlled rate.
    - Service
        - Serves as a load balancer to balance traffic across a set of pods.
        - You are allowed to specify which type of service you would like to use:
            - ClusterIP: exposes the service on a cluster-internalIP.
            - NodePort: exposes the service on each node’s IP at a static port (the NodePort)
            - Load Balancer: exposes the service externally using a cloud provider’s load balancer.
- **Workload Resources**
    - [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/)
        - A ReplicaSet’s purpose is to maintain a stable set of replica pods running at any given time. As such, it is often used to guarantee the availability of a specified number of identical pods
    - [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)
        - A StatefulSet is the workload API object used to manage stateful applications.
        - Manages the deployment and scaling of a set of pods, *and provides guarantees about the ordering and uniqueness of these pods.*
        - Like a deployment, a StatefulSet manages pods that are based on an identical container spec.
        - Unlike a deployment, a StatefulSet maintains a sticky identity for each of their pods. These pods are created from the same spec, but are not interchangeable: each has a persistent identifier that it maintains across any rescheduling.
    - [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)
        - A DaemonSet ensures that all (or some) nodes run a copy of a pod. As nodes are added to the cluster, pods are added to them. As nodes are removed from the cluster, those pods are garbage collected. Deleting a DaemonSet will clean up the pods it created.
    - ConfigMaps
        - ConfigMaps enable you to separate your configurations from your pods and components, which helps keep your workloads portable.
- **GKE Sandbox**
    - Provides a second layer of security between containerized workloads on GKE.
    - GKE Sandbox uses gVisor.
    - You cannot enable GKE Sandbox on a default node pool.
    - When using Sandbox, you must have at least 2 node pools.
    - It’s not possible to use accelerations such as GPUs or TPUs.
 

### DaemonSet 
A DaemonSet ensures that all (or some) Nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected.  


### Kubernetes Logs  
Kubernetes Engine collects application logs by default when the log data is written to:  
- `STDOUT`  
- `STDERR`

### Node Auto-Upgrades in GKE
This feature ensures that the nodes in your cluster are always up-to-date with the latest stable and supported version of Kubernetes. Google handles the upgrade process in a manner that aims to minimize downtime by carefully managing the upgrade of nodes. It is a key feature to maintain the reliability, security, and operational health of your applications.

