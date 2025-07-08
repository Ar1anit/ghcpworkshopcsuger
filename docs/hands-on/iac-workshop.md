# Infrastructure as Code Workshop with GitHub Copilot 🚀

In this comprehensive hands-on workshop, you'll learn how to leverage GitHub Copilot to accelerate your infrastructure development and streamline your cloud deployments using Terraform and Azure!

## Workshop Overview 📋

**Duration**: 5.5 hours (including breaks)  
**Difficulty**: Intermediate to Advanced  
**Prerequisites**: Basic knowledge of cloud computing, Terraform, and Azure  

## What You'll Build 🏗️

A complete infrastructure deployment pipeline with the following components:
- Azure infrastructure using Terraform with GitHub Copilot assistance
- CI/CD pipeline with GitHub Actions
- Security-first architecture with best practices
- Multi-environment deployment strategy
- Monitoring and observability setup

## Workshop Objectives 🎯

By the end of this workshop, you will be able to:
- ✅ Use GitHub Copilot to generate Infrastructure as Code templates
- ✅ Accelerate Terraform and Azure Bicep development
- ✅ Apply best practices for IaC with AI assistance
- ✅ Debug and optimize infrastructure code using Copilot
- ✅ Implement CI/CD pipelines for infrastructure deployment

## Prerequisites 📋

Before starting this workshop, ensure you have:
- 🔧 **GitHub Copilot** subscription and VS Code extension installed
- 🔷 **GitHub Copilot for Azure** extension installed
- ☁️ **Azure Account** with appropriate permissions
- 🛠️ **Tools Installed**:
  - Git
  - Terraform CLI
  - Azure CLI
  - VS Code with relevant extensions

## Workshop Structure 🏗️

### Module 1: Getting Started with GitHub Copilot for IaC 🌟
**Duration**: 45 minutes

Learn the fundamentals of using GitHub Copilot for infrastructure development:
- Introduction to GitHub Copilot capabilities for infrastructure code
- Setting up your development environment
- Writing your first IaC template with Copilot assistance
- Effective prompting strategies for infrastructure code

**What You'll Learn**:
- How Copilot understands infrastructure patterns
- Context awareness in IaC files
- Multi-language support (Terraform, ARM, Bicep, YAML)

### Module 2: Terraform Development with Copilot 🏭
**Duration**: 60 minutes

Deep dive into Terraform development with AI assistance:
- Generating complex Terraform resources using Copilot
- Creating reusable modules with AI assistance
- Mastering variable definitions and outputs
- Implementing Terraform best practices

**Hands-On Exercise**: Create a comprehensive networking module and storage module with security features.

### Module 3: Azure Template Development 🌐
**Duration**: 75 minutes

Master Azure-specific infrastructure templates:
- Generate Azure Resource Manager (ARM) templates with Copilot
- Azure Bicep development using AI assistance
- Template conversion between formats
- Apply Azure-specific best practices

**Hands-On Exercise**: Build a complete web application infrastructure using both ARM and Bicep templates.

### Module 4: Advanced IaC Patterns 🔒
**Duration**: 90 minutes

Implement complex infrastructure patterns and security:
- Generate complex infrastructure patterns using Copilot
- Implement security and compliance best practices
- Create testable infrastructure code
- Use advanced Terraform and Azure features

**Hands-On Exercise**: Create a hub-and-spoke architecture with comprehensive security controls.

### Module 5: 🚀 Challenge - Deploy with GitHub Copilot Agent Mode
**Duration**: 90 minutes

**This is the exciting finale!** A team-based challenge where you'll use GitHub Copilot's agent mode (@workspace) and the GitHub Copilot for Azure extension to deploy infrastructure.

**Challenge Mission**: Deploy a secure, scalable web application on Azure including:
- App Service with custom domain
- Azure SQL Database with failover
- Application Insights for monitoring
- Azure Key Vault for secrets
- CDN for static content

**Team Competition**: Work in teams of 2-3 people to complete the deployment fastest while following best practices!

## Key Features of This Workshop 🌟

### 🤖 GitHub Copilot Agent Mode
Learn to use the powerful @workspace agent for:
- Infrastructure planning and analysis
- Code generation and debugging
- Best practice recommendations
- Troubleshooting assistance

### 🔷 GitHub Copilot for Azure Extension
Leverage Azure-specific AI assistance:
- Generate Azure CLI commands
- Get architectural recommendations
- Implement monitoring and alerting
- Security configuration guidance

### 🏆 Gamification Elements
- Team-based challenges
- Scoring system for code quality
- Special awards for innovation
- Competitive deployment race

## Sample Code Examples 💻

### Terraform with Copilot
```hcl
# Create a secure Azure App Service with SQL Database
# Include all security best practices and monitoring
resource "azurerm_resource_group" "main" {
  name     = "rg-webapp-${var.environment}"
  location = var.location
  
  tags = {
    Environment = var.environment
    Project     = var.project_name
  }
}

# Let Copilot generate the rest of the infrastructure...
```

### Using Agent Mode
```
@workspace Can you help me analyze the current infrastructure requirements and create a plan for deploying a secure web application on Azure using Terraform?

@azure What are the best practices for App Service deployment?

@workspace Generate a GitHub Actions workflow for multi-environment deployment
```

## Learning Outcomes 📚

After completing this workshop, participants will:

1. **Increased Productivity**: Generate infrastructure code 3x faster with Copilot
2. **Better Code Quality**: Implement security and best practices consistently
3. **AI-Assisted Development**: Master prompting strategies for infrastructure code
4. **Modern DevOps**: Implement CI/CD pipelines with automated testing
5. **Azure Expertise**: Apply Azure-specific patterns and configurations

## Tips for Success 💡

### 🎯 Effective Prompting Strategies
- Use descriptive comments to guide Copilot
- Break complex requirements into smaller parts
- Iterate and refine suggestions
- Always review generated code for security

### 🔷 Leverage Azure Extension
- Use @azure agent for Azure-specific guidance
- Generate CLI commands for setup tasks
- Get architectural recommendations
- Implement monitoring best practices

### 🏗️ Best Practices
- Start with security in mind
- Use modular design patterns
- Implement proper testing
- Document your infrastructure

## Workshop Resources 📚

### Documentation Links
- [GitHub Copilot Documentation](https://docs.github.com/copilot)
- [Terraform Best Practices](https://www.terraform.io/docs/cloud/guides/recommended-practices/index.html)
- [Azure Architecture Center](https://docs.microsoft.com/azure/architecture/)

### Workshop Files
The workshop includes comprehensive materials:
```
hands-on/iac/tf-workshop/
├── module-1/          # Getting Started
├── module-2/          # Terraform Development
├── module-3/          # Azure Templates
├── module-4/          # Advanced Patterns
├── module-5/          # Challenge Mode
└── instructor-guide.md # For instructors
```

## Scoring and Recognition 🏆

### Challenge Scoring Matrix
| Category | Points | Description |
|----------|--------|-------------|
| **Agent Mode Usage** | 40 | Extensive use of @workspace for all tasks |
| **Azure Extension** | 20 | @azure used for guidance and commands |
| **Infrastructure Quality** | 30 | Secure, scalable, well-documented |
| **CI/CD Pipeline** | 30 | Full automation with testing |
| **Code Quality** | 10 | Excellent structure and documentation |

### Special Awards
- 🎨 **Best Use of Agent Mode** - Most creative @workspace usage
- 🔒 **Security Champion** - Best security implementation
- 🏗️ **Innovation Award** - Most unique solution

## Getting Started 🚀

1. **Clone the workshop repository**
2. **Verify your tools and extensions are installed**
3. **Authenticate with Azure CLI**
4. **Enable GitHub Copilot in VS Code**
5. **Join your team for the challenge**

## Next Steps After the Workshop 🔄

- Apply techniques to real-world projects
- Explore advanced Copilot features
- Share learnings with your team
- Continue building with AI assistance

---

**Ready to revolutionize your infrastructure development with AI? Let's build the future of cloud infrastructure together!** 🌟

*This workshop demonstrates how GitHub Copilot can transform not just application development, but infrastructure management and deployment as well.*

![IaC Workshop](../assets/images/iac-workshop-banner.png)
