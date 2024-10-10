## Terraform  
Terraform is a tool used for implementing infrastructure as code and managing cloud infrastructure.   

### Terraform directory  
Terraform uses configuration files to define infrastructure elements. These files are written in the Terraform language with a `.tf` extension.  

#### Root Module
- main.tf: The primary configuration file for the root module.  
- servers/: A subdirectory containing child modules (e.g., for servers).
 
#### Child Module
- main.tf: The primary configuration file for the child module.  
- providers.tf: Defines the providers (e.g., AWS, GCP) used in the module.  
- variables.tf: Declares input variables that can be passed to the module.  
- outputs.tf: Defines outputs that can be exported from the module.  
- terraform.tfvars: A file for storing variable values (optional).

Terraform commands are run on the working directory.  


### HCL syntax  
```terraform
resource "google_compute_network" "default" {
  name                    = "mynetwork"
  auto_create_subnetowrks = false
}
```

### Terraform commands  
- **terraform init**	Initializes the provider with plugins.
- **terraform plan**	Creates a preview of the resources that will be created after running terraform apply.
- **terraform apply**	Creates real infrastructure resources based on the plan.
- **terraform destroy**	Destroys the existing infrastructure resources.
- **terraform fmt** Auto format to match canonical conventions


### Meta-arguments for resources   
- **count**	Creates multiple instances of a resource based on a specified number.
- **for_each**	Creates multiple instances of a resource based on a set of strings.
- **depends_on**	Specifies dependencies between resources, ensuring that one resource is created or updated before another.
- **lifecycle**	Defines the lifecycle behavior of a resource, such as actions to take before or after creation or deletion.
- **provider**	Selects a non-default provider configuration for a resource.

### Terraform state  
In Terraform, state is a critical concept that keeps track of the infrastructure managed by Terraform. The state file records the current status of resources created, updated, or deleted, ensuring that Terraform has an accurate view of what exists in your infrastructure.  

The state file (`terraform.tfstate`) is used by Terraform to map real-world resources to the configuration defined in the `.tf` files.  

#### View the current state  
```bash
terraform show
```

#### List resources in the state file
```bash
terraform state list
```   

#### State Locking
When using a remote backend, Terraform locks the state during operations, preventing multiple people from making changes simultaneously, which could lead to inconsistencies.


## Key Features of Terraform  
- **Declarative Language**: Terraform uses the HashiCorp Configuration Language (HCL)
- **Provider System**: Terraform uses "providers" to communicate with APIs of different cloud platforms. Examples include:
   - `google` provider for Google Cloud Platform (GCP)
   - `aws` provider for AWS
- **Infrastructure as Code**: With Terraform, infrastructure is defined as code, enabling version control, collaboration, and automation of infrastructure deployment.
- **State Management**: Terraform maintains a state file (terraform.tfstate), which tracks the current state of your infrastructure. This helps Terraform to understand what resources are present and if they need to be modified, added, or deleted.
- **Execution Plan**: Terraform generates an execution plan with the terraform plan command, showing what actions will be performed before making changes. This allows you to review and confirm changes before applying them.
- **Modular Design**: Terraform encourages the use of modules, which are reusable packages of code for common infrastructure patterns.
