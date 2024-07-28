## Cloud Storage  
- **Used for**
    - Unstructured data:  
      - Images  
      - Video  
      - Text
    - Archived data
    - Temporary storage between services
    - Global access, internet accessible
- **Logical Organization**
    - Global namespace  
    - Buckets  
    - Folders  
    - Objects
- **Bucket Configurations**
    - Life Cycle Management
        - You can define conditions that trigger data deletion, or transition to a cheaper storage class with object class with object life cycle management.
    - Versioning
        - Continue to store old copies of objects you store when they are deleted or overwritten.
    - Retention Policies
        - Define minimum retention periods that objects must be stored.
    - Object Holds
        - Place an object on hold to prevent deletion
    - Encryption Keys
        - Customer-managed
        - Customer-supplied
    - Access Permissions
        - Access Control list
        - Uniform bucket level access
        - Object and Bucket Level Permissions
- **Storage Classes:**
    - Stanard Storage
        - Frequent
        - Optimized for performance
    - Backup and Archival
        - Nearline stored at least 30 days
        - Coldline stored at least 90 days
        - Archive stored at least 365 days
    - Read or modify on average once in those time periods
    - [https://cloud.google.com/storage/docs/storage-classes](https://cloud.google.com/storage/docs/storage-classes)
- **[Uploading Objects to Google Cloud Storage](https://cloud.google.com/storage/docs/uploads-downloads)**
    - Simple Upload
        - Utilize this if the file is small enough to upload again if the connection fails, and if there is **no** object metadata to send as part of the upload request.
    - Multipart Upload
        - Utilize this if the file is small enough to upload again if the connection fails, and you **need** to include object metadata as part of the upload request.
    - Resumable Upload
        - Utilize this for a more reliable transfer, which is especially important with large files.
    - [Parallel Composite Upload](https://cloud.google.com/storage/docs/parallel-composite-uploads)
        - Utilize if network and disk speed are not limiting factors. When doing parallel composite upload, a file is divided into up to 32 chunks and uploaded in parallel to temporary objects. The final object is recreated using the temporary objects, and the temporary objects are deleted.
    - Alternatively, for uploading large volumes of data (from hundreds of terabytes up to 1 petabyte), you can utilize **Transfer Appliance**. It is a hardware appliance you can use to securely migrate to Google Cloud Platform without disrupting business operations.
 
### Pricing
 Data storage pricing is based on the amount of data and storage type.
 
### Cloud Storage Object Lifecycle Management
- `Cloud Storage Object Lifecycle Management` allows you to define a set of rules that manage the lifecycle of your objects. The Age condition specifies the number of days since the object's creation.  
- The `SetStorageClass` action changes the storage class of objects within the bucket. Setting it to 90 days means that 90 days after the object's creation, it will be moved to Coldline Storage.  
- The Delete action specifies when the object should be deleted.

Change storage class:  
`gsutil rewrite -s Coldline gs://PATH_TO_OBJECT`  

Creation and content type of objects:  
`gsutil stat gs://BUCKET_NAME/OBJECT_NAME`  


### Change storage class  
`gcloud storage rewrite -s Coldline gs://PATH_TO_OBJECT`  

### Metada in Cloud Storage object  
`gsutil stat gs://BUCKET_NAME/OBJECT_NAME`  

### Access to Cloud Storage  
Access is granted to Cloud Storage objects using IAM or access control lists (ACLs). When `uniform bucket-level access` is applied, users only have access through IAM roles and permissions. A users that could access objects before uniform bucket-level access is applied but not after must have had access through ACLs.
