# IaC Workshop Quick Reference Guide

## Terraform Commands

```bash
# Initialize working directory
terraform init

# Validate configuration
terraform validate

# Format code
terraform fmt

# Create execution plan
terraform plan

# Apply changes
terraform apply

# Destroy infrastructure
terraform destroy

# Show current state
terraform show

# List resources in state
terraform state list

# Import existing resource
terraform import <resource_type>.<name> <azure_resource_id>

# Unlock state (use with caution)
terraform force-unlock <lock_id>

# Create new workspace
terraform workspace new <name>

# List workspaces
terraform workspace list

# Switch workspace
terraform workspace select <name>
```

## Bicep Commands

```bash
# Install Bicep
az bicep install

# Upgrade Bicep
az bicep upgrade

# Check version
az bicep version

# Build template (validate)
az bicep build --file main.bicep

# Decompile ARM to Bicep
az bicep decompile --file template.json

# Create resource group
az group create --name <rg-name> --location <location>

# Deploy to resource group
az deployment group create \
  --resource-group <rg-name> \
  --template-file main.bicep \
  --parameters parameters.json

# Deploy to subscription
az deployment sub create \
  --location <location> \
  --template-file main.bicep

# Validate deployment
az deployment group validate \
  --resource-group <rg-name> \
  --template-file main.bicep

# What-if analysis
az deployment group what-if \
  --resource-group <rg-name> \
  --template-file main.bicep

# List deployments
az deployment group list \
  --resource-group <rg-name>

# Show deployment details
az deployment group show \
  --resource-group <rg-name> \
  --name <deployment-name>

# Delete resource group
az group delete --name <rg-name> --yes
```

## Azure CLI Authentication

```bash
# Login to Azure
az login

# Login with specific tenant
az login --tenant <tenant-id>

# List subscriptions
az account list --output table

# Show current subscription
az account show

# Set active subscription
az account set --subscription <subscription-id>

# List locations
az account list-locations --output table

# Login with service principal
az login --service-principal \
  --username <app-id> \
  --password <password> \
  --tenant <tenant-id>
```

## GitHub Copilot Prompts

### Terraform Prompts

```hcl
# Create a storage account with secure transfer and TLS 1.2

# Create a virtual network with three subnets: web, app, and data

# Add an App Service Plan with Standard S1 tier for Linux

# Create a Key Vault with soft delete and purge protection enabled

# Generate a random password for the SQL Server admin

# Output the storage account primary connection string as sensitive

# Create a network security group with rules for HTTP, HTTPS, and SSH

# Add an Azure SQL Server with Microsoft Entra authentication

# Create a container registry with admin access disabled
```

### Bicep Prompts

```bicep
// Create a storage account with blob containers for uploads and backups

// Add a web app with managed identity and application insights

// Create a virtual network with DDoS protection enabled

// Generate a Key Vault with RBAC authorization model

// Add a SQL database with zone redundancy

// Create a private endpoint for the storage account

// Configure diagnostic settings for all resources

// Add a user-assigned managed identity for the app service
```

## Common Resource Name Prefixes

| Resource Type | Prefix | Example |
|--------------|--------|---------|
| Resource Group | rg- | rg-workshop-dev |
| Virtual Network | vnet- | vnet-hub-prod |
| Subnet | snet- | snet-frontend |
| Network Security Group | nsg- | nsg-web |
| Storage Account | st | stwkshpdev001 |
| Key Vault | kv- | kv-app-prod |
| App Service Plan | asp- | asp-web-prod |
| App Service | app- | app-api-prod |
| Function App | func- | func-process-prod |
| SQL Server | sql- | sql-main-prod |
| SQL Database | sqldb- | sqldb-app-prod |
| Container Registry | cr | crwkshpprod001 |
| Cosmos DB | cosmos- | cosmos-app-prod |
| Application Insights | appi- | appi-web-prod |

## Azure Regions (Common)

| Display Name | CLI Name |
|--------------|----------|
| East US | eastus |
| East US 2 | eastus2 |
| West US | westus |
| West US 2 | westus2 |
| Central US | centralus |
| North Europe | northeurope |
| West Europe | westeurope |
| UK South | uksouth |
| Southeast Asia | southeastasia |
| Japan East | japaneast |
| Australia East | australiaeast |

## Useful Copilot Chat Commands

```
# Get help with Terraform
@workspace How do I set up remote state for Terraform?

# Deployment assistance
@workspace Deploy my Terraform configuration to Azure

# Debugging
@workspace Why is my deployment failing with this error: [error]

# Best practices
@workspace What security best practices should I follow for Azure storage accounts?

# Cost optimization
@workspace How can I reduce costs for this infrastructure?

# Module creation
@workspace Create a reusable module for an App Service with Application Insights

# Documentation
@workspace Generate documentation for my Terraform configuration

# Migration
@workspace Help me migrate from ARM templates to Bicep
```

## Terraform Variable Types

```hcl
# String
variable "location" {
  type        = string
  description = "Azure region"
  default     = "eastus"
}

# Number
variable "instance_count" {
  type    = number
  default = 2
}

# Bool
variable "enable_https" {
  type    = bool
  default = true
}

# List
variable "allowed_ips" {
  type    = list(string)
  default = ["10.0.0.0/24", "10.0.1.0/24"]
}

# Map
variable "tags" {
  type = map(string)
  default = {
    Environment = "dev"
    Project     = "workshop"
  }
}

# Object
variable "vm_config" {
  type = object({
    size     = string
    os_type  = string
    disk_gb  = number
  })
}
```

## Bicep Parameter Decorators

```bicep
@description('The Azure region for resources')
param location string = resourceGroup().location

@minLength(3)
@maxLength(24)
param storageAccountName string

@allowed([
  'dev'
  'staging'
  'prod'
])
param environment string

@secure()
param adminPassword string

@minValue(1)
@maxValue(100)
param instanceCount int = 2

@metadata({
  description: 'The pricing tier'
  example: 'Standard_LRS'
})
param storageSku string
```

## Resource Dependencies

### Terraform
```hcl
# Implicit dependency (automatic)
resource "azurerm_subnet" "example" {
  virtual_network_name = azurerm_virtual_network.example.name
}

# Explicit dependency
resource "azurerm_storage_account" "example" {
  depends_on = [azurerm_resource_group.example]
}
```

### Bicep
```bicep
// Implicit dependency (automatic)
resource subnet 'Microsoft.Network/virtualNetworks/subnets@2023-04-01' = {
  parent: virtualNetwork
  name: 'subnet1'
}

// Explicit dependency
resource storageAccount 'Microsoft.Storage/storageAccounts@2023-01-01' = {
  dependsOn: [
    resourceGroup
  ]
}
```

## Troubleshooting Tips

### Issue: Terraform State Locked
```bash
# View lock info
terraform force-unlock <lock-id>

# Or delete lock manually in Azure Portal
# Go to Storage Account > Container > Blob
```

### Issue: Bicep Deployment Failed
```bash
# View detailed error
az deployment group show \
  --resource-group <rg-name> \
  --name <deployment-name> \
  --query properties.error

# Check deployment history
az deployment operation group list \
  --resource-group <rg-name> \
  --name <deployment-name>
```

### Issue: Name Already Taken
```hcl
# Terraform - use random provider
resource "random_string" "unique" {
  length  = 8
  special = false
  upper   = false
}

resource "azurerm_storage_account" "example" {
  name = "st${random_string.unique.result}"
}
```

```bicep
// Bicep - use uniqueString function
var storageAccountName = 'st${uniqueString(resourceGroup().id)}'
```

## Security Checklist

- [ ] Enable HTTPS/TLS for all endpoints
- [ ] Use managed identities instead of connection strings
- [ ] Enable encryption at rest
- [ ] Enable encryption in transit
- [ ] Restrict network access with NSGs
- [ ] Use private endpoints for PaaS services
- [ ] Store secrets in Key Vault
- [ ] Enable diagnostic logging
- [ ] Use latest API versions
- [ ] Follow principle of least privilege
- [ ] Enable Microsoft Defender for Cloud
- [ ] Tag all resources appropriately
- [ ] Use resource locks for critical resources
- [ ] Enable soft delete on Key Vaults
- [ ] Disable public access to storage accounts

## Additional Resources

- [Terraform Azure Provider Docs](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
- [Bicep Documentation](https://learn.microsoft.com/azure/azure-resource-manager/bicep/)
- [Azure CLI Reference](https://learn.microsoft.com/cli/azure/)
- [Azure Naming Conventions](https://learn.microsoft.com/azure/cloud-adoption-framework/ready/azure-best-practices/resource-naming)
- [Azure Resource Manager Templates Reference](https://learn.microsoft.com/azure/templates/)

---

**Pro Tip**: Keep this guide handy during the workshop! Use Ctrl+F to quickly find commands and examples.
