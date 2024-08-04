### Cloud Memorystore  
A cache is an in-memory data store designed to provide applications with sub milisecond access to data, this is low latency storate system. Caches are limited in size by the amount of memory available.  
If the machine hosting the cache shuts down, then the contents of the cache are lost.  

### MemoryStore  
GCP offers Memorystore, a managed Redis service. Redis is a widely used open source cache. Since Memorystore is protocol with Redis, tools and applications written to work with Redis should work with Memorystore.  
When you use Memorystore, you create and instances that run Redis.  

Connect from:  
- App Engine
- Compute Engine VMs
- Cloud Functions
- Cloud Run
- GKE cluster

Memory configuration:  
- from 1GB to 300GB

Redis protocol compliant  

Basic Tier:
  - cache with no replication  
  - no cross zone replication  
  - no automatic failover

Standard Tier:  
  - cache with replication
  - cross zone replication
  - automatic failover

### Memcached 
- Distributed in-memory key-value store
- Instance is one cluster
- Configure:
    - Number of nodes
    - Number of vCPUs
    - Memory
  - Maximum 20 nodes
  - All nodes have same configuration
  - 1 to 32 vCPUS
  - 1 GB to 256 GB per node
  - Maximum 5 TB in an instance





