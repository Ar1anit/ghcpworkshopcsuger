# Module 3: Azure Template Development 🌐

## 📚 Learning Objectives
By the end of this module, participants will:
- Generate Azure Resource Manager (ARM) templates with Copilot
- Master Azure Bicep development using AI assistance
- Understand template conversion between formats
- Apply Azure-specific best practices

## ⏱️ Duration
75 minutes

## 🎯 Module Content

### 3.1 ARM Template Generation (25 minutes)
**Instructor Demo:**
Generate ARM templates for common Azure patterns:

```json
// Create ARM template for web app with database
// Include App Service, SQL Database, and Key Vault
// Add parameters and variables section
```

**Key Points:**
- ARM template structure and syntax
- Parameter definitions and default values
- Resource dependencies in ARM

### 3.2 Azure Bicep Development (30 minutes)
**Guided Exercise:**
Use Copilot to create Bicep templates:

```bicep
// Create a Bicep template for a complete web application
// Include App Service Plan, Web App, SQL Server, and Database
// Add monitoring with Application Insights
```

**Teaching Focus:**
- Bicep syntax advantages over ARM
- Type safety and IntelliSense
- Module composition in Bicep

### 3.3 Template Conversion and Migration (10 minutes)
**Hands-on Activity:**
- Convert ARM templates to Bicep using Copilot
- Migrate from Terraform to Bicep
- Best practices for template conversion

### 3.4 Azure-Specific Patterns (10 minutes)
**Instructor Notes:**
Cover Azure-specific infrastructure patterns:
- Hub and spoke networking
- Azure landing zones
- Security and compliance templates

## 🛠️ Hands-On Exercises

### Exercise 3.1: Complete Web Application (ARM)
**Time:** 30 minutes

**Instructions:**
1. Create ARM template for a web application
2. Include all necessary Azure resources
3. Use Copilot for parameter validation

**Required Resources:**
- Resource Group
- App Service Plan
- Web App
- SQL Server and Database
- Application Insights
- Key Vault

### Exercise 3.2: Same Application in Bicep
**Time:** 25 minutes

**Instructions:**
1. Recreate the same infrastructure using Bicep
2. Compare complexity and readability
3. Add modular design with Bicep modules

### Exercise 3.3: Multi-Environment Template
**Time:** 20 minutes

**Instructions:**
1. Create parameterized templates for multiple environments
2. Use Copilot for environment-specific configurations
3. Include proper tagging and naming conventions

## 📁 Exercise Files
```
exercises/
├── arm-templates/
│   ├── web-app-complete.json
│   ├── parameters.dev.json
│   └── parameters.prod.json
├── bicep-templates/
│   ├── main.bicep
│   ├── modules/
│   │   ├── web-app.bicep
│   │   └── database.bicep
│   └── parameters/
└── examples/
    ├── hub-spoke-network/
    └── landing-zone/
```

## 🔧 Azure CLI Commands
```bash
# Deploy ARM template
az deployment group create --resource-group myRG --template-file main.json

# Deploy Bicep template
az deployment group create --resource-group myRG --template-file main.bicep

# Validate template
az deployment group validate --resource-group myRG --template-file main.bicep
```

## 📝 Key Takeaways
- Bicep offers better developer experience than ARM JSON
- Copilot understands Azure resource relationships
- Always validate templates before deployment
- Use modules for reusable components

## 🔗 Next Module
[Module 4: Advanced IaC Patterns](../module-4/README.md)
