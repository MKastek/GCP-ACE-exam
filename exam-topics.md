## Table of Contents
* Main exam topics to know 
  * Kubernetes
  * Compute Engine
  * App Engine
  * Cloud Storage
  * Databases
  * Virtual Private Cloud (VPC)
  * Cloud Logging
  * Cloud Monitoring
  * Cloud IAM
  * Cloud Billing


## Resources Used for Preparation


## Main exam topics to know 



---

### Cloud Logging

- **Features**
    - Write any custom log, from any source, into Cloud Logging using the public write APIs.
    - Integrates with Cloud Monitoring to set alerts on the logs events and logs-based metrics you have defined.
    - You can export data in real-time to BigQuery to perform advanced analytics and SQL-like query tasks.
    - Cloud Logging helps you see the problems with your data using Error Reporting. It helps you automatically analyze your logs for exceptions and intelligently aggregate them into meaningful error groups.
- **Cloud Audit Logs**
    - Admin Activity admin logs
        - Contains log entries for API calls or other administrative actions that modify the configuration or metadata or resources.
        - You must have the IAM role logging/logs.viewer or project/viewer to view these logs.
        - Admin Activity logs are always written and you can’t configure or disable them in any way.
    - Data Access audit logs
        - Contains API calls that read the configuration or metadata of resources, including user-driven API calls that create, modify, or read user-provided resource data.
        - You must have logging/private.logs.viewer or project/owner to view these logs.
        - You must explicitly enable Data Access audit logs to be written. They are disabled by default because they are large.
    - System Event audit logs
        - Contains log entries for administrative actions taken by Google Cloud that modify the configuration of resources.
        - You must have the IAM role logging/logs.viewer or project/viewer to view these logs.
        - System Event audit logs are always written so you can’t configure or disable them.
        - There is no additional charge for your System Event audit logs.
    - Exporting Audit Logs
        - Log entries received by Logging can be exported to Cloud Storage buckets, BigQuery datasets. and Pub/Sub topics.
        - To export audit log entries outside of logging:
            - Create a logs sink.
            - Give the sink a query that specifies the audit log types you want to export.
        - If you want to export audit log entries for a Google Cloud organization, folder, or billing account, review Aggregated sinks.

### Cloud Monitoring

- **Workspaces**
    - A Workspace can manage the monitoring of data for a single Google Cloud project, or it can manage the data for multiple Google Cloud projects and AWS accounts.
        - A Google Cloud project or an AWS account can only be associated with one Workspace at a time.
    - You must have the following IAM role name for the Google Cloud project to create a Workspace:
        - Monitoring Editor
        - Monitoring Admin
        - Project Owner
- **Cloud Monitoring Agent**
    - The Cloud Monitoring agent is a `collectd` based daemon that collects application and system metrics from virtual machine instances.
    - The Monitoring agent collects disk, network, CPU, and process metrics by default.
    - You can configure the Monitoring agent to monitor third-party applications.

---

### Cloud IAM

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
---

### Cloud Billing

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
