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
