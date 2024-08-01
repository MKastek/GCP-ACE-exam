## Cloud Run  
- Compute service for stateless containers
- Avaialable in two forms:
    - Managed service
    - Anthos
### Managed service  
- When you use managed service you pay per use with limitations:
    - 1000 services per region
    - 2 GB memory per container instance
    - 2 vCPUs per container instance

### Cloud Run Resources
- Service is the main abstraction of computing in Cloud Run:
    - Located in a region
    - Replicted across multiple zones
- Revision is a deployment of a service - consists of a specific image and a configuration.
- Container instances run revisions, autoscale based on load

### Concurrency  
- Container instance can receive up to 80 requests at at the same time.
- Possible to reduce concurrency to 1 (when high consuming requests, image not designed to handle multiple requests).
