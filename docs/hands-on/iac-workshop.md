# Infrastructure as Code with GitHub Copilot Workshop 🏗️

Welcome to the Infrastructure as Code (IaC) workshop! In this hands-on session, you'll learn how to leverage GitHub Copilot to accelerate your infrastructure development using both Terraform and Bicep.

## Workshop Overview 📋

| Section | Duration | Description |
|---------|----------|-------------|
| Introduction | 15 mins | Understanding GitHub Copilot & IaC |
| Terraform Generations | 30 mins | Creating Azure resources with Terraform |
| Bicep Generations | 30 mins | Building infrastructure with Bicep |
| Cross-Translation | 20 mins | Converting between Bicep and Terraform |
| Deployment with Agent Mode | 25 mins | Deploying resources using GitHub Copilot Agent |

**Total Duration**: ~2 hours

---

## 1. Introduction to GitHub Copilot and IaC 🚀

### What is Infrastructure as Code?

Infrastructure as Code (IaC) is the practice of managing and provisioning infrastructure through machine-readable definition files, rather than physical hardware configuration or interactive configuration tools.

**Key Benefits**:
- ✅ **Version Control**: Track infrastructure changes over time
- ✅ **Consistency**: Deploy identical environments repeatedly
- ✅ **Automation**: Reduce manual configuration errors
- ✅ **Documentation**: Code serves as living documentation
- ✅ **Collaboration**: Team members can review and contribute

### GitHub Copilot for IaC

GitHub Copilot accelerates IaC development by:
- 🤖 Generating resource definitions from natural language comments
- 🔄 Suggesting best practices and common patterns
- 📝 Auto-completing complex configurations
- 🔍 Helping with syntax and provider-specific attributes
- 🛡️ Suggesting security and compliance configurations

### Tools We'll Use

**Terraform**:
- Cloud-agnostic IaC tool
- Uses HCL (HashiCorp Configuration Language)
- Large provider ecosystem
- State management built-in

**Bicep**:
- Azure-native IaC language
- Cleaner syntax than ARM templates
- Direct integration with Azure
- Automatically manages state

### Prerequisites

Before starting, ensure you have:
- [ ] Visual Studio Code installed
- [ ] GitHub Copilot extension enabled
- [ ] Azure CLI installed (`az --version`)
- [ ] Terraform installed (`terraform --version`)
- [ ] Bicep CLI installed (`az bicep version`)
- [ ] Azure subscription access

---

## 2. Generations with Terraform 🌍

In this section, you'll use GitHub Copilot to generate Terraform configurations for various Azure resources.

### Exercise 2.1: Setting Up a Terraform Project

**Objective**: Create a basic Terraform project structure with provider configuration.

1. **Create a new directory** for your Terraform project:
   ```bash
   mkdir terraform-workshop
   cd terraform-workshop
   ```

2. **Create `main.tf`** and start with a comment:
   ```hcl
   # Configure Azure provider with required features
   ```

3. **Let GitHub Copilot complete** the provider configuration. You should see suggestions similar to:
   ```hcl
   terraform {
     required_providers {
       azurerm = {
         source  = "hashicorp/azurerm"
         version = "~> 3.0"
       }
     }
   }

   provider "azurerm" {
     features {}
   }
   ```

4. **Create `variables.tf`** with common variables:
   ```hcl
   # Variable for resource group location
   ```
   
   Let Copilot suggest the variable definition.

### Exercise 2.2: Creating a Resource Group

**Objective**: Generate Terraform code to create an Azure Resource Group.

1. **In `main.tf`, add a comment**:
   ```hcl
   # Create a resource group in East US for the workshop
   ```

2. **Accept Copilot's suggestion**. It should generate something like:
   ```hcl
   resource "azurerm_resource_group" "workshop" {
     name     = "rg-workshop-demo"
     location = "East US"
   }
   ```

3. **Try variations** with different prompts:
   ```hcl
   # Create a resource group with tags for environment and project
   ```

### Exercise 2.3: Creating a Virtual Network

**Objective**: Generate a complete virtual network with subnets.

1. **Add a comment for VNet creation**:
   ```hcl
   # Create a virtual network with address space 10.0.0.0/16 and two subnets
   ```

2. **Let Copilot generate** the virtual network and subnet configurations.

3. **Enhance with a comment**:
   ```hcl
   # Add a network security group with rules for HTTP and HTTPS
   ```

**Expected Output**:
```hcl
resource "azurerm_virtual_network" "main" {
  name                = "vnet-workshop"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.workshop.location
  resource_group_name = azurerm_resource_group.workshop.name
}

resource "azurerm_subnet" "frontend" {
  name                 = "subnet-frontend"
  resource_group_name  = azurerm_resource_group.workshop.name
  virtual_network_name = azurerm_virtual_network.main.name
  address_prefixes     = ["10.0.1.0/24"]
}

resource "azurerm_subnet" "backend" {
  name                 = "subnet-backend"
  resource_group_name  = azurerm_resource_group.workshop.name
  virtual_network_name = azurerm_virtual_network.main.name
  address_prefixes     = ["10.0.2.0/24"]
}
```

### Exercise 2.4: Creating a Storage Account

**Objective**: Generate a secure storage account with best practices.

1. **Use a descriptive comment**:
   ```hcl
   # Create a storage account with encryption enabled and deny public access
   ```

2. **Let Copilot suggest** the configuration with security settings.

3. **Add blob container**:
   ```hcl
   # Create a private blob container for application data
   ```

### Exercise 2.5: Creating an App Service

**Objective**: Generate a complete App Service environment.

**Prompt Sequence**:
```hcl
# Create an App Service Plan with Standard S1 SKU for Linux

# Create an App Service for a Node.js application with application insights

# Configure app settings for the web app including connection strings
```

**Tips for Better Generations**:
- 💡 Be specific about SKUs, tiers, and configurations
- 💡 Mention dependencies explicitly (e.g., "using the resource group created above")
- 💡 Request security features (managed identity, HTTPS only, etc.)
- 💡 Ask for outputs to retrieve important values

### Exercise 2.6: Outputs and Data Sources

1. **Create `outputs.tf`** and add:
   ```hcl
   # Output the resource group name and id
   
   # Output the app service default hostname
   
   # Output the storage account primary connection string as sensitive
   ```

2. **Create `data.tf`** for data sources:
   ```hcl
   # Data source to get current Azure subscription information
   ```

### 🎯 Challenge: Complete Infrastructure

Try generating a complete infrastructure setup with:
- Resource Group
- Virtual Network with 3 subnets
- Storage Account
- Key Vault with secret
- App Service Plan + App Service
- SQL Database
- Application Insights

Use comments to guide Copilot and see how much it can generate!

---

## 3. Generations with Bicep 💪

In this section, you'll use GitHub Copilot to generate Bicep templates for Azure resources.

### Exercise 3.1: Setting Up a Bicep Project

**Objective**: Create a basic Bicep template structure.

1. **Create a new directory**:
   ```bash
   mkdir bicep-workshop
   cd bicep-workshop
   ```

2. **Create `main.bicep`** and start with:
   ```bicep
   // Target scope for the deployment
   ```

3. **Let Copilot complete** the target scope and add parameter definitions:
   ```bicep
   targetScope = 'resourceGroup'

   // Parameters for location and environment
   ```

### Exercise 3.2: Creating a Resource Group (Subscription Level)

**Objective**: Generate a subscription-level deployment for resource group creation.

1. **Create `resourceGroup.bicep`**:
   ```bicep
   targetScope = 'subscription'
   
   // Create a resource group for the workshop with tags
   ```

2. **Accept Copilot's suggestions** for parameters and resource definition.

### Exercise 3.3: Creating a Storage Account

**Objective**: Generate a storage account with best practices.

1. **In `main.bicep`, add**:
   ```bicep
   // Create a storage account with secure defaults and blob containers
   ```

2. **Enhance the prompt**:
   ```bicep
   // Storage account with:
   // - Secure transfer required
   // - Minimum TLS 1.2
   // - Deny public blob access
   // - GRS replication
   ```

**Expected Output**:
```bicep
resource storageAccount 'Microsoft.Storage/storageAccounts@2023-01-01' = {
  name: 'stwkshp${uniqueString(resourceGroup().id)}'
  location: location
  kind: 'StorageV2'
  sku: {
    name: 'Standard_GRS'
  }
  properties: {
    supportsHttpsTrafficOnly: true
    minimumTlsVersion: 'TLS1_2'
    allowBlobPublicAccess: false
    encryption: {
      services: {
        blob: {
          enabled: true
        }
        file: {
          enabled: true
        }
      }
      keySource: 'Microsoft.Storage'
    }
  }
}
```

### Exercise 3.4: Creating a Web App with App Service Plan

**Objective**: Generate App Service infrastructure.

1. **Add to `main.bicep`**:
   ```bicep
   // Create an App Service Plan with Linux and B1 tier
   
   // Create a Web App for Node.js 18 LTS
   ```

2. **Add configuration**:
   ```bicep
   // Configure web app with managed identity and HTTPS only
   ```

### Exercise 3.5: Creating a Key Vault

**Objective**: Generate a secure Key Vault with access policies.

**Prompt**:
```bicep
// Create a Key Vault with:
// - Soft delete enabled
// - Purge protection enabled
// - Access policy for current deployment user
// - Private endpoint ready configuration
```

### Exercise 3.6: Using Modules

**Objective**: Learn to create and use Bicep modules.

1. **Create `modules/storage.bicep`**:
   ```bicep
   // Module for creating a storage account with configurable parameters
   ```

2. **In `main.bicep`, use the module**:
   ```bicep
   // Use the storage module to create a storage account
   ```

**Expected Output**:
```bicep
module storage './modules/storage.bicep' = {
  name: 'storageDeployment'
  params: {
    storageAccountName: 'stwkshp${uniqueString(resourceGroup().id)}'
    location: location
    sku: 'Standard_LRS'
  }
}
```

### Exercise 3.7: Outputs and Parameters

1. **Create `parameters.json`**:
   ```json
   // Parameter file with development environment values
   ```

2. **Add outputs to `main.bicep`**:
   ```bicep
   // Output the web app URL and storage account name
   ```

### Exercise 3.8: Creating a Virtual Network with NSGs

**Prompt Sequence**:
```bicep
// Create a virtual network with three subnets: frontend, backend, and database

// Create network security groups for each subnet with appropriate rules

// Associate NSGs with subnets
```

### 🎯 Challenge: Multi-Tier Application

Create a complete Bicep template for a multi-tier application:
- Virtual Network with subnets
- Application Gateway
- App Service Plan + 2 Web Apps
- SQL Database with private endpoint
- Storage Account
- Key Vault
- Application Insights
- All resources using managed identities where possible

---

## 4. From Bicep to Terraform and Vice Versa 🔄

In this section, you'll learn how to convert between Bicep and Terraform using GitHub Copilot.

### Exercise 4.1: Bicep to Terraform Conversion

**Objective**: Convert an existing Bicep template to Terraform.

1. **Start with a Bicep template** (`storage.bicep`):
   ```bicep
   resource storageAccount 'Microsoft.Storage/storageAccounts@2023-01-01' = {
     name: 'stwkshp${uniqueString(resourceGroup().id)}'
     location: location
     kind: 'StorageV2'
     sku: {
       name: 'Standard_LRS'
     }
     properties: {
       supportsHttpsTrafficOnly: true
       minimumTlsVersion: 'TLS1_2'
       allowBlobPublicAccess: false
     }
   }
   ```

2. **Create `storage.tf` and add a comment**:
   ```hcl
   # Convert the following Bicep template to Terraform:
   # [paste the Bicep code as a comment]
   ```

3. **Let Copilot generate** the Terraform equivalent.

**Alternative Approach - Using Copilot Chat**:
1. Open Copilot Chat
2. Paste your Bicep code
3. Prompt: "Convert this Bicep template to Terraform HCL"

### Exercise 4.2: Terraform to Bicep Conversion

**Objective**: Convert Terraform configuration to Bicep.

1. **Start with Terraform** (`app-service.tf`):
   ```hcl
   resource "azurerm_service_plan" "main" {
     name                = "asp-workshop"
     location            = azurerm_resource_group.main.location
     resource_group_name = azurerm_resource_group.main.name
     os_type             = "Linux"
     sku_name            = "B1"
   }

   resource "azurerm_linux_web_app" "main" {
     name                = "app-workshop-${random_string.unique.result}"
     location            = azurerm_resource_group.main.location
     resource_group_name = azurerm_resource_group.main.name
     service_plan_id     = azurerm_service_plan.main.id

     site_config {
       application_stack {
         node_version = "18-lts"
       }
     }
   }
   ```

2. **Create `app-service.bicep`**:
   ```bicep
   // Convert the following Terraform configuration to Bicep:
   // [paste Terraform code as comment]
   ```

3. **Let Copilot convert** the configuration.

### Exercise 4.3: Complex Conversion - Virtual Network

**Challenge**: Convert a complete virtual network setup including:
- VNet with multiple subnets
- Network Security Groups with rules
- Subnet-NSG associations
- Network Interfaces

**Steps**:
1. Choose either Bicep or Terraform as your starting point
2. Create the complete configuration
3. Convert to the other language using Copilot
4. Compare both implementations

### Exercise 4.4: Module/Module Conversion

**Objective**: Convert a Bicep module to a Terraform module.

1. **Bicep Module** (`modules/database.bicep`):
   ```bicep
   @description('SQL Server name')
   param sqlServerName string

   @description('SQL Database name')
   param sqlDatabaseName string

   @description('Location for resources')
   param location string = resourceGroup().location

   resource sqlServer 'Microsoft.Sql/servers@2022-05-01-preview' = {
     name: sqlServerName
     location: location
     properties: {
       administratorLogin: 'sqladmin'
       administratorLoginPassword: 'P@ssw0rd123!'
     }
   }

   resource sqlDatabase 'Microsoft.Sql/servers/databases@2022-05-01-preview' = {
     parent: sqlServer
     name: sqlDatabaseName
     location: location
     sku: {
       name: 'Basic'
     }
   }

   output sqlServerId string = sqlServer.id
   ```

2. **Convert to Terraform module** structure with proper directory layout and variable definitions.

### Exercise 4.5: State and Configuration Differences

**Discussion Points**:

**Terraform State**:
```hcl
# Terraform maintains state in terraform.tfstate
# Initialize backend for remote state
terraform {
  backend "azurerm" {
    resource_group_name  = "rg-terraform-state"
    storage_account_name = "sttfstate"
    container_name       = "tfstate"
    key                  = "workshop.tfstate"
  }
}
```

**Bicep Deployment**:
```bicep
// Bicep uses Azure's deployment history
// No separate state file needed
// Deployment tracked in Azure Resource Manager
```

### 🎯 Conversion Challenge

Convert a complete infrastructure between Bicep and Terraform:
- Resource Group
- Virtual Network
- App Service Plan + Web App
- SQL Server + Database
- Storage Account
- Key Vault
- All outputs

Compare:
- ✅ Syntax differences
- ✅ Resource dependencies
- ✅ Parameter/variable handling
- ✅ Output definitions
- ✅ Module structure

---

## 5. Deploying Resources with Terraform x Agent Mode 🤖

In this section, you'll use GitHub Copilot's Agent Mode to deploy and manage infrastructure.

### What is Agent Mode?

GitHub Copilot Agent Mode allows Copilot to:
- 🔍 Analyze your infrastructure code
- 🛠️ Execute commands on your behalf
- 🐛 Debug deployment issues
- 📊 Provide deployment insights
- 🔄 Iterate on configurations

### Exercise 5.1: Setting Up for Deployment

**Objective**: Prepare your environment for Terraform deployment.

1. **Open Copilot Chat** and ask:
   ```
   @workspace I want to deploy my Terraform configuration. 
   Help me prepare the environment and check prerequisites.
   ```

2. **Copilot will help you**:
   - Verify Azure CLI login status
   - Check Terraform installation
   - Initialize the Terraform working directory
   - Validate your configuration

3. **Follow the suggestions** to run:
   ```bash
   az login
   az account show
   terraform init
   terraform validate
   ```

### Exercise 5.2: Planning the Deployment

**Objective**: Use Agent Mode to create and review a deployment plan.

1. **Ask Copilot**:
   ```
   @workspace Create a Terraform plan for my infrastructure. 
   Show me what resources will be created.
   ```

2. **Copilot will**:
   - Run `terraform plan`
   - Analyze the output
   - Explain what changes will occur
   - Highlight any potential issues

3. **Review the plan** and ask follow-up questions:
   ```
   Why is the storage account being replaced?
   What are the security implications of this configuration?
   ```

### Exercise 5.3: Deploying Infrastructure

**Objective**: Deploy your infrastructure using Terraform with Copilot's guidance.

1. **Request deployment**:
   ```
   @workspace Deploy the Terraform configuration to Azure. 
   Walk me through the process step by step.
   ```

2. **Copilot will guide you through**:
   - Reviewing the plan one more time
   - Confirming resource creation
   - Executing `terraform apply`
   - Monitoring the deployment progress

3. **Handle any errors** with Copilot's help:
   ```
   The deployment failed with error [paste error]. 
   How can I fix this?
   ```

### Exercise 5.4: Managing State

**Objective**: Work with Terraform state using Agent Mode.

1. **Query state**:
   ```
   @workspace Show me the current state of my infrastructure. 
   What resources are currently deployed?
   ```

2. **Copilot will run**:
   ```bash
   terraform show
   terraform state list
   ```

3. **Advanced state operations**:
   ```
   @workspace I need to remove the storage account from Terraform 
   state without deleting the actual resource. How do I do this?
   ```

**Expected Guidance**:
```bash
terraform state rm azurerm_storage_account.example
```

### Exercise 5.5: Debugging Deployment Issues

**Scenario**: Your deployment fails with a common error.

1. **Share the error with Copilot**:
   ```
   @workspace My Terraform deployment failed with this error:
   
   Error: creating Storage Account: 
   storage.AccountsClient#Create: Failure sending request: 
   StatusCode=409 -- Original Error: 
   Code="StorageAccountAlreadyExists" Message="The storage 
   account named 'mystorageaccount' is already taken."
   
   How can I fix this?
   ```

2. **Copilot will suggest**:
   - Using `uniqueString()` or random provider
   - Checking if resource already exists
   - Importing existing resource
   - Modifying the naming convention

3. **Apply the fix** with Copilot's help:
   ```
   @workspace Update my Terraform configuration to use a unique 
   storage account name that won't conflict.
   ```

### Exercise 5.6: Incremental Updates

**Objective**: Add new resources to existing infrastructure.

1. **Request changes**:
   ```
   @workspace Add an Azure Container Registry to my existing 
   infrastructure. It should be in the same resource group and 
   use a Standard SKU.
   ```

2. **Copilot will**:
   - Generate the ACR resource configuration
   - Add it to your `main.tf`
   - Create a plan showing the new resource
   - Deploy the change

3. **Verify the update**:
   ```
   @workspace Show me the newly created container registry 
   and its login server URL.
   ```

### Exercise 5.7: Destruction and Cleanup

**Objective**: Safely remove infrastructure with Copilot's guidance.

1. **Plan destruction**:
   ```
   @workspace I want to destroy all resources created by 
   Terraform. Show me what will be deleted first.
   ```

2. **Copilot will run**:
   ```bash
   terraform plan -destroy
   ```

3. **Selective destruction**:
   ```
   @workspace Remove only the storage account and its 
   related resources, but keep everything else.
   ```

4. **Execute cleanup**:
   ```
   @workspace Proceed with destroying all resources. 
   Confirm before execution.
   ```

### Exercise 5.8: Multi-Environment Deployment

**Objective**: Deploy to multiple environments using workspaces.

1. **Setup workspaces**:
   ```
   @workspace Help me set up Terraform workspaces for dev, 
   staging, and production environments.
   ```

2. **Copilot will guide you**:
   ```bash
   terraform workspace new dev
   terraform workspace new staging
   terraform workspace new prod
   ```

3. **Environment-specific deployment**:
   ```
   @workspace Deploy to the dev workspace with smaller 
   SKUs and different naming convention.
   ```

4. **Create `environments/dev.tfvars`** with Copilot's help:
   ```
   @workspace Create a dev.tfvars file with appropriate 
   settings for a development environment - smaller SKUs, 
   basic tiers, and dev naming suffix.
   ```

### Exercise 5.9: Continuous Integration Setup

**Objective**: Create a GitHub Actions workflow for Terraform deployment.

1. **Request workflow creation**:
   ```
   @workspace Create a GitHub Actions workflow that:
   - Runs terraform plan on pull requests
   - Runs terraform apply on merge to main
   - Stores state in Azure Storage
   - Uses OIDC for authentication
   ```

2. **Copilot will generate** `.github/workflows/terraform.yml` with:
   - Checkout steps
   - Terraform setup
   - Azure login with OIDC
   - Plan and apply stages
   - PR commenting with plan output

3. **Add necessary secrets**:
   ```
   @workspace What secrets do I need to configure in GitHub 
   for this workflow to work?
   ```

### Exercise 5.10: Cost Analysis

**Objective**: Understand the cost implications of your infrastructure.

1. **Ask for cost estimation**:
   ```
   @workspace Analyze my Terraform configuration and estimate 
   the monthly cost of running this infrastructure in Azure.
   ```

2. **Copilot will**:
   - Review resource SKUs and tiers
   - Provide approximate costs per resource
   - Suggest cost optimization options

3. **Optimize costs**:
   ```
   @workspace Suggest ways to reduce the cost of this 
   infrastructure without significantly impacting performance.
   ```

### 🎯 Final Challenge: Complete Deployment Pipeline

Using Agent Mode, create a complete end-to-end deployment pipeline:

1. **Infrastructure Setup**:
   - Resource Group
   - Virtual Network
   - App Service Plan + Web App
   - SQL Database
   - Storage Account
   - Application Insights

2. **Deployment Process**:
   - Initialize Terraform with remote state
   - Create and review plan
   - Deploy to dev environment
   - Validate deployment
   - Promote to staging
   - Promote to production

3. **Automation**:
   - GitHub Actions workflow
   - PR validation
   - Automatic deployment
   - State management

4. **Monitoring**:
   - Output all connection strings and URLs
   - Verify all resources are accessible
   - Check Application Insights integration

**Prompt to Start**:
```
@workspace I need to deploy a complete multi-tier web application 
infrastructure to Azure with dev, staging, and production 
environments. Guide me through creating the Terraform configuration, 
setting up remote state, creating a CI/CD pipeline, and deploying 
to all environments.
```

---

## Best Practices and Tips 💡

### Working with GitHub Copilot for IaC

**Do's** ✅:
- Write descriptive comments explaining your intent
- Break complex infrastructure into modules
- Request security best practices explicitly
- Ask Copilot to add outputs for important values
- Use consistent naming conventions
- Request validation and error handling
- Ask for documentation comments

**Don'ts** ❌:
- Don't accept suggestions without reviewing them
- Don't hardcode secrets or sensitive values
- Don't ignore security warnings
- Don't skip validation steps
- Don't deploy to production without testing

### Effective Prompting for IaC

**Good Prompts**:
```
✅ "Create a storage account with secure transfer required, 
   minimum TLS 1.2, and blob soft delete enabled"

✅ "Generate an App Service with managed identity, HTTPS only, 
   and application insights integration"

✅ "Create a virtual network with three subnets: web (10.0.1.0/24), 
   app (10.0.2.0/24), and data (10.0.3.0/24)"
```

**Poor Prompts**:
```
❌ "Create storage"
❌ "Add web app"
❌ "Make a database"
```

### Security Considerations

When generating IaC with Copilot:
- 🔐 Always enable encryption at rest and in transit
- 🔐 Use managed identities instead of connection strings
- 🔐 Enable audit logging
- 🔐 Restrict network access with NSGs and private endpoints
- 🔐 Use Key Vault for secrets
- 🔐 Enable Microsoft Defender for Cloud
- 🔐 Follow the principle of least privilege

### State Management

**Terraform**:
```hcl
# Always use remote state for team collaboration
terraform {
  backend "azurerm" {
    resource_group_name  = "rg-terraform-state"
    storage_account_name = "sttfstate"
    container_name       = "tfstate"
    key                  = "prod.tfstate"
  }
}
```

**Bicep**:
- No separate state file needed
- Azure tracks deployments automatically
- Use deployment history for troubleshooting

---

## Troubleshooting Common Issues 🔧

### Issue 1: Provider Version Conflicts

**Symptom**: Terraform fails with provider version errors

**Solution with Copilot**:
```
@workspace My Terraform deployment is failing with provider 
version conflicts. Here's the error: [paste error]. 
How can I fix the version constraints?
```

### Issue 2: Circular Dependencies

**Symptom**: Resources depend on each other creating a cycle

**Solution with Copilot**:
```
@workspace I have a circular dependency in my infrastructure 
code. Resource A depends on B, and B depends on A. 
How can I restructure this?
```

### Issue 3: Name Already Exists

**Symptom**: Resource names must be globally unique

**Solution with Copilot**:
```
@workspace Generate unique names for my Azure resources 
that won't conflict with existing resources.
```

### Issue 4: Insufficient Permissions

**Symptom**: Deployment fails due to RBAC issues

**Solution with Copilot**:
```
@workspace My deployment failed with an authorization error. 
What permissions do I need to deploy this infrastructure?
```

### Issue 5: State Lock

**Symptom**: Terraform state is locked by another process

**Solution with Copilot**:
```
@workspace My Terraform state is locked. How can I safely 
unlock it and continue with my deployment?
```

---

## Additional Resources 📚

### Documentation
- [Terraform Azure Provider](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
- [Bicep Documentation](https://learn.microsoft.com/azure/azure-resource-manager/bicep/)
- [Azure Architecture Center](https://learn.microsoft.com/azure/architecture/)

### Tools
- [Terraform Cloud](https://cloud.hashicorp.com/products/terraform)
- [Azure Bicep Playground](https://aka.ms/bicepdemo)
- [Azure Resource Manager Template Reference](https://learn.microsoft.com/azure/templates/)

### GitHub Copilot Tips
- [Copilot for Azure](https://learn.microsoft.com/azure/copilot/)
- [GitHub Copilot Best Practices](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/)

---

## Workshop Completion Checklist ✅

- [ ] Completed Introduction to IaC and GitHub Copilot
- [ ] Generated Terraform configurations for multiple Azure resources
- [ ] Created Bicep templates for Azure infrastructure
- [ ] Converted between Bicep and Terraform
- [ ] Deployed infrastructure using Terraform with Agent Mode
- [ ] Set up multi-environment deployment
- [ ] Created CI/CD pipeline for IaC
- [ ] Implemented security best practices
- [ ] Practiced troubleshooting with Copilot

---

## Next Steps 🚀

After completing this workshop, consider:

1. **Expand Your Skills**:
   - Learn about Terraform modules and registries
   - Explore Bicep advanced features like loops and conditions
   - Study Azure Policy for governance

2. **Build Real Projects**:
   - Deploy a complete application infrastructure
   - Set up monitoring and alerting
   - Implement disaster recovery

3. **Contribute to the Community**:
   - Share your Terraform modules
   - Create Bicep samples
   - Write about your IaC journey

4. **Stay Updated**:
   - Follow Azure updates
   - Track new Terraform provider features
   - Monitor GitHub Copilot enhancements

---

## Feedback and Support 💬

We'd love to hear about your experience!

- Share your feedback on the workshop
- Report issues or suggest improvements
- Connect with other participants

Happy Infrastructure Coding with GitHub Copilot! 🎉
