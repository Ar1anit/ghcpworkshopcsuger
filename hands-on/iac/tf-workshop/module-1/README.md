# Module 1: Getting Started with GitHub Copilot for IaC 🌟

## 📚 Learning Objectives
By the end of this module, participants will:
- Understand GitHub Copilot's capabilities for infrastructure code
- Set up their development environment optimally
- Write their first IaC template with Copilot assistance
- Learn effective prompting strategies for infrastructure code

## ⏱️ Duration
45 minutes

## 📋 Prerequisites Check
Ensure participants have:
- ✅ GitHub Copilot enabled in VS Code
- ✅ Terraform CLI installed (`terraform --version`)
- ✅ Azure CLI installed (`az --version`)
- ✅ Git configured

## 🎯 Module Content

### 1.1 Introduction to GitHub Copilot for IaC (10 minutes)
**Instructor Notes:**
- Explain how Copilot understands infrastructure patterns
- Demonstrate real-time code generation
- Show the difference between regular code completion and AI assistance

**Key Points to Cover:**
- Copilot's training on infrastructure code patterns
- Context awareness in IaC files
- Multi-language support (Terraform, ARM, Bicep, YAML)

### 1.2 Environment Setup Verification (10 minutes)
**Hands-on Activity:**
Have participants verify their setup:

```bash
# Check tools
terraform --version
az --version
git --version

# Verify Copilot in VS Code
# Open VS Code and check for Copilot icon in status bar
```

### 1.3 Your First IaC Template with Copilot (20 minutes)
**Guided Exercise:**

1. Create a new file: `main.tf`
2. Start typing: `# Create an Azure resource group`
3. Let Copilot suggest the Terraform code
4. Accept and modify suggestions

**Expected Output:**
```hcl
# Create an Azure resource group
resource "azurerm_resource_group" "main" {
  name     = "rg-workshop-${random_string.suffix.result}"
  location = var.location
}
```

### 1.4 Effective Prompting Strategies (5 minutes)
**Instructor Demonstration:**

Good prompts:
```
# Create a storage account with blob encryption
# Add network security group with SSH rule
# Generate variables for environment configuration
```

Poor prompts:
```
# storage
# network stuff
# variables
```

## 🛠️ Hands-On Exercise

### Exercise 1.1: Basic Resource Group and Storage
**Time:** 15 minutes

**Instructions:**
1. Create a new Terraform file
2. Use comments to prompt Copilot for:
   - Resource group
   - Storage account
   - Variables file
3. Review and understand generated code

**Success Criteria:**
- [ ] Resource group with dynamic naming
- [ ] Storage account with secure defaults
- [ ] Proper variable definitions

## 📝 Key Takeaways
- GitHub Copilot accelerates IaC development
- Context and comments are crucial for good suggestions
- Always review generated code for best practices
- Copilot learns from your coding patterns

## 🔗 Next Module
[Module 2: Terraform Development with Copilot](../module-2/README.md)
