## App Engine  
- Platform as Service
- Serverless managed service
- Originally limited to languge specific runtimes, now can run custom containters  
- **Standard and Flexible environment**
    - Standard
        - Based on container instances running on Google’s infrastructure.
    - Flexible
        - Enables you to manage the underlying compute infrastructure.
- **Scaling**
    - Basic
        - Creates instances when your application receives requests.
        - Each instance will be shut down when the application becomes idle.
    - Automatic Scaling
        - Creates instance based on request rate, response latencies, or application metrics that you specify.
    - Manual Scaling
        - Allows you to manually specify the number of instances that continuously run regardless of the load level.
- Deploying an App Engine service with CLI.


### App Engine  
App Engine is designed for applications written in supported languages, that need to run at low cost, and need to scale in response to rapid increases in load. App Engine is a managed service and as such minimizes operational overhead.

#### cron.yaml 
Cron.yaml files contain specifications for running scheduled jobs in App Engine.

#### app.yaml
App.yaml has overall application specifications.  

#### App Engine Standard  
App Engine Standard i a platform as a service (PaaS), you do not have to manage underlying infrastructure. It provides a secure sandbox environment for deploying new features quickly. 
