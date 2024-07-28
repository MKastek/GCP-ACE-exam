## App Engine  

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
