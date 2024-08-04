## Cloud Billing  

- **Cloud Billing Account**
    - Access control to Cloud Billing account is established by IAM roles.
- **Google Payments Profile**
    - Stores information about who is responsible for the profile
    - Serves as a document center where you can view invoices and payment history.
- **Cloud Billing Reports**
    - The Cloud Billing Reports page allows you to view your Google Cloud usage costs at a glance and discover and analyze trends.
    - You can also forecast future costs using the Cloud Billing Reports to check out how much you are projected to spend, up to 12 months in the future.
- **Cloud Billing Budgets**
    - You can define the scope of the budget to apply:
        - Entire Cloud Billing account.
        - One or more projects.
        - One or more products.
        - Other budget filters applicable to your Cloud Billing account.
    - You can specify the budget amount to your requirement, or base the budget amount on the previous month’s spend.
    - Moreover, you can also specify email alerts and declare the recipients in the following ways:
        - Using the role-based option, where you can send email alerts to billing admins and users on the Cloud Billing account.
        - Using Cloud Monitoring, where you can enlist other people in your organization to receive budget alert emails.
        - You can also use Pub/Sub for a more programmatic notification approach.
- **Overview of Cloud Billing Roles in IAM**
    - Billing Account Creator (roles/billing.creator)
        - Create new self-service billing accounts.
        - Assigned at the organization level.
        - Use this role for initial billing setup or to allow the creation of additional billings. Users must have this role to sign up for Google Cloud with a credit card using their corporate identity.
    - Billing Account Administrator (roles/billing.admin)
        - Manage billing accounts (but not create them).
        - Can be assigned at the organization level or billing account.
        - This role is an owner role for a billing account. Use it to manage payment instruments, configure billing exports, view cost information, link and unlink projects, and manage other user riles on the billing account.
    - Billing Account User (roles/billing.user)
        - Link projects to billing accounts.
        - Can be assigned at the organization level or billing account.
        - This role has very restricted permissions, so you can grant it broadly, typically in combination with Project Creator. These two roles allow a user to create new projects linked to the billing account on which the role is granted.
    - Billing Account Viewer
        - View billing account cost information and transactions.
        - Can be assigned at the organization level or billing account.
        - Billing Account Viewer access would usually be granted to finance teams. It provides access to spend information but does not confer the right to link or unlink projects or otherwise manage the properties of the billing account.
    - Project Billing Manager (roles/billing.projectManager)
        - Link/unlink the project to/from a billing account.
        - Can be assigned at the organization level or billing account.
        - This role allows a user to attach the project to the billing account, but does not grant any rights over resources. Project Owners can use this role to allow someone else to manage the billing for the project without granting them resource access.


### Billing accounts in Google Cloud
-  Project and its resources can only be tied to one billing account.
-  Billing account can handle billing for more than one project.

### Allocation quotas   
Setting up quotas for the resources will prevent resource consumption from exceeding specified limits.  

Allocation quotas, also known as resource quotas, define the number of resources that your project has access to. Compute Engine enforces allocation quotas on resource usage for various reasons. For example, quotas help to protect the community of Google Cloud users by preventing unforeseen spikes in usage.  

Allocation quotas are the maximum number of resources you can create of that resource type, if those resources are available. 
