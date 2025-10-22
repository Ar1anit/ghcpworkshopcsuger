# Infrastructure as Code Workshop Files

This directory contains supporting files and examples for the IaC x GitHub Copilot workshop.

## Directory Structure

```
iac/
├── terraform-examples/    # Terraform configuration examples
├── bicep-examples/        # Bicep template examples
└── README.md             # This file
```

## Getting Started

1. **Prerequisites**:
   - Install [Terraform](https://www.terraform.io/downloads)
   - Install [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
   - Install Bicep: `az bicep install`
   - Enable GitHub Copilot in VS Code

2. **Authentication**:
   ```bash
   az login
   az account set --subscription "Your-Subscription-Name"
   ```

3. **Choose Your Path**:
   - Start with `terraform-examples/` for Terraform exercises
   - Start with `bicep-examples/` for Bicep exercises
   - Or follow the workshop guide at `../../docs/hands-on/iac-workshop.md`

## Quick Start Commands

### Terraform
```bash
cd terraform-examples
terraform init
terraform plan
terraform apply
```

### Bicep
```bash
cd bicep-examples
az deployment group create \
  --resource-group <your-rg> \
  --template-file main.bicep
```

## Tips for Using GitHub Copilot

- Start with descriptive comments explaining what you want to create
- Be specific about SKUs, regions, and configurations
- Ask for security best practices explicitly
- Use Copilot Chat (@workspace) for complex questions
- Review all generated code before applying

## Need Help?

Refer to the main workshop document: `../../docs/hands-on/iac-workshop.md`
