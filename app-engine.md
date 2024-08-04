## App Engine  
- Platform as Service
- Serverless managed service
- Originally limited to languge specific runtimes, now can run custom containters  
- **Standard and Flexible environment**
    - Standard
        - Based on container instances running on Google’s infrastructure.
        - Run applications in preconfigured containers.
        - Autoscales
        - Python, Java, Go, Ruby, PHP, Node.js
    - Flexible
        - Enables you to manage the underlying compute infrastructure.
        - Customized Docker container (other language support).
        - Higher CPU and memory limites
        - Applications run in regional managed instance groups - not zonal.
- **Scaling**
    - Basic
        - Creates instances when your application receives requests.
        - Each instance will be shut down when the application becomes idle.
    - Automatic Scaling
        - Creates instance based on request rate, response latencies, or application metrics that you specify.
    - Manual Scaling
        - Allows you to manually specify the number of instances that continuously run regardless of the load level.
- Deploying an App Engine service with CLI.



### Configuring Autoscaling  
- Configured in app.yaml
- Configuration options include:
    - Target_cpu_utilization
    - Target_throughput_utilization
    - Max_concurrent_requests
    - Max_pending_latency
    - Min pending_latency

 Instances are created to execute an application on an App Engine managed server. App Engine can automatically add or remove instances as needed based on load. When instances are scaled based on load, they are called `dynamic` instances. These dynamic instances help optimize your costs by shutting down when demand is low. 
   
 Your configuration determines wheter an instance is resident or dynamic. If you configure `autoscaling` or `basic scaling`, then instances will be dynamic.   
 If you configure `manual scaling` then your instances will be resident.  
 
### App Engine  
App Engine is designed for applications written in supported languages, that need to run at low cost, and need to scale in response to rapid increases in load. App Engine is a managed service and as such minimizes operational overhead.

#### cron.yaml 
Cron.yaml files contain specifications for running scheduled jobs in App Engine.

#### app.yaml
App.yaml has overall application specifications.  

#### App Engine Standard  
App Engine Standard i a platform as a service (PaaS), you do not have to manage underlying infrastructure. It provides a secure sandbox environment for deploying new features quickly. 


### App Engine Traffic Splitting  
- If more than one version of an app running, you can split traffic between versions.
- 3 ways to split trafiic:  
      - IP address  
      - HTTP cookie  
      - Random selection

### Traffic Splitting by Cookie  
- Preferred method of traffic splitting
- HTTP request header for cookie named `GOOGAPPUID` with hash value
- Hash value determines instance to route traffic too

### gcloud command  
To deploy your app, you can use the following command:  
`gcloud app deploy app.yml`  
with optional parameters:  
- `--version` to specify a custom version ID  
- `--project` to specify the project ID to use for this app  
- `--no-promote` to deploy the app without routing traffic to it  

You can stop serving versions using the `gcloud app versions stop` command:  
`gcloud app versions stop v1`  

