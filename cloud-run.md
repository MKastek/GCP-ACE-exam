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

### Cloud Run Service
- Service is the main abstraction of computing in Cloud Run:
    - Located in a region
    - Replicted across multiple zones
- Revision is a deployment of a service - consists of a specific image and a configuration.
- Container instances run revisions, autoscale based on load

### Concurrency  
- Container instance can receive up to 80 requests at at the same time.
- Possible to reduce concurrency to 1 (when high consuming requests, image not designed to handle multiple requests).


### Cloud Run Job  
- Completed job (processing data, reporting)  
- Good option for batch job
- Variables, secrets, connections, security configuration

### Cloud Run summary  
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
