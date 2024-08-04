## Cloud IAM  
- **Features**
    - Lets you authorize who can take specific actions on resources to give you full control and visibility on your Google Cloud services centrally.
    - Permissions are represented in the forms of *service.resource.verb.*
- **Roles**
    - A role contains a set of permissions that allows you to perform specific actions on Google Cloud resources.
    - You don’t directly grant users permissions in IAM. Instead, you grant them roles, which bundle one or more permissions.
    - Types of roles:
        - Basic roles
            - Owner, Editor, and Viewer.
        - Predefined Roles
            - Provides granular access for a specific service and is managed and defined by Google Cloud.
        - Custom Roles
            - Provides granular access according to a user-defined list of permissions.
            - You can create a custom IAM role with one or more permissions and then grant that custom role to users or groups.
- **Service Accounts**
    - Used by an application or a virtual machine instance, not a person.
    - Applications use service accounts to make authorized API calls.
    - A service account is associated with two sets of public/private RSA key pairs used to authenticate to Google.
    - Types of service accounts
        - User-managed service accounts
        - Default service accounts
            - Google creates a user-managed service account when you use Google Cloud services. These accounts are called default service accounts.
            - In addition to being an identity, **a service account is also a resource** with IAM policies attached to it, which means you can define who can use the account and who can perform specific actions on the service account.
- **Best** **Practices**
    - Enforce least privilege at all times.
    - Mirror your Google Cloud resource hierarchy structure to your organization structure.
    - Set policies at the organization level and at the project level rather than at the resource level.
    - It’s easier and better to manage members in a Google group than to update an IAM policy.
    - Rotate your service account keys using the IAM service account API.
    - For production workloads, it’s best practice to user user-managed service accounts instead of the default service accounts.


### IAM users and roles assigned within a GCP 
The IAM section in the Google Cloud Console provides a comprehensive view of all IAM members (users, service accounts, groups, etc.) and their assigned roles within the selected project. It allows you to verify who has access to what resources within your project and with which permissions.  


### Principle of least privilege
Give just enough permissions to perform the required tasks  


 ### gcloud iam roles copy  
 gcloud iam roles copy - create a role from an existing role  
```
gcloud iam roles copy [--dest-organization=DEST_ORGANIZATION] [--dest-project=DEST_PROJECT]
[--destination=DESTINATION] [--source=SOURCE] [--source-organization=SOURCE_ORGANIZATION]  
[--source-project=SOURCE_PROJECT]  
```
