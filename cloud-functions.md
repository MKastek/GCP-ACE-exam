## Cloud Functions  
- Serverless compute service with 2 generations of functionality
- Execute code in response to events based on triggers
- Available in multiple services

### Events  
- Storage
    - Upload
    - Delete
    - Archive

- Cloud Pub/Sub
    - Publish a message

- HTTP
  - POST
  - GET
  - PUT
  - DELETE
  - OPTIONS

- Firebase  

- Logging  

### Functions  
Supported langunages: Node.js, Python, Go, Java, Ruby, PHP  
Memory allocation  

### Time limits  
By default, the functions will time out after 1 minute, although you can set the timemout for as long as 9 minutes.   

### Memory Allocated  
Memory allocated is the amount that will be available to the function. Memory options range from **128MB to 2GB**.  

### gcloud commands for Cloud Functions  
`gcloud functions deploy`  
`gcloud functions delete`  

