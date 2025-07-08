# Module 2: Terraform Development with Copilot 🏭

## 📚 Learning Objectives
By the end of this module, participants will:
- Generate complex Terraform resources using Copilot
- Create reusable modules with AI assistance
- Master variable definitions and outputs
- Implement Terraform best practices

## ⏱️ Duration
60 minutes

## 🎯 Module Content

### 2.1 Advanced Resource Generation (20 minutes)
**Instructor Demo:**
Show how to generate complex Azure resources:

```hcl
# Create a virtual network with multiple subnets
# Add network security groups with custom rules
# Configure Azure Key Vault with access policies
```

**Key Teaching Points:**
- How Copilot understands resource dependencies
- Generating multiple related resources
- Using Copilot for resource naming conventions

### 2.2 Creating Terraform Modules (20 minutes)
**Guided Exercise:**

1. Create `modules/` directory structure
2. Generate a networking module
3. Use Copilot for module variables and outputs

**Expected Structure:**
```
modules/
├── networking/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
└── storage/
    ├── main.tf
    ├── variables.tf
    └── outputs.tf
```

### 2.3 Variables and Outputs Best Practices (15 minutes)
**Hands-on Activity:**
Use Copilot to generate:
- Comprehensive variable definitions with descriptions
- Validation rules for variables
- Meaningful outputs with descriptions

### 2.4 Code Organization Patterns (5 minutes)
**Instructor Notes:**
- File naming conventions
- Directory structure best practices
- When to use modules vs. resources

## 🛠️ Hands-On Exercises

### Exercise 2.1: Networking Module
**Time:** 25 minutes

**Instructions:**
1. Create a networking module using Copilot
2. Include VNet, subnets, NSGs, and route tables
3. Add comprehensive variables and outputs

**Starter Prompt:**
```hcl
# Create a comprehensive Azure networking module
# Include VNet with public and private subnets
# Add network security groups with default rules
# Configure route tables for subnet routing
```

### Exercise 2.2: Storage Module with Security
**Time:** 20 minutes

**Instructions:**
1. Generate a secure storage account module
2. Include encryption, access controls, and monitoring
3. Use Copilot for security best practices

## 📁 Exercise Files
- `exercises/networking-module/`
- `exercises/storage-module/`
- `examples/complete-infrastructure/`

## 📝 Key Takeaways
- Copilot excels at generating boilerplate Terraform code
- Modular design improves reusability and maintainability
- Always validate generated security configurations
- Use descriptive comments for better AI suggestions

## 🔗 Next Module
[Module 3: Cloud Provider Templates](../module-3/README.md)
