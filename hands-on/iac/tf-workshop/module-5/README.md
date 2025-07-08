# Module 5: 🚀 Challenge - Deploy Terraform with GitHub Copilot Agent Mode & Azure Extension

## 🎯 Challenge Overview
This is a **hands-on challenge** where you'll use GitHub Copilot's agent mode (@workspace) and the GitHub Copilot for Azure extension to deploy infrastructure. You'll work in teams and compete to complete the deployment fastest while following best practices!

## 🏆 Challenge Objectives
Teams will compete to:
- ✅ Use GitHub Copilot agent mode (@workspace) for infrastructure planning
- ✅ Leverage GitHub Copilot for Azure extension for Azure-specific guidance
- ✅ Deploy a complete web application infrastructure using Terraform
- ✅ Implement CI/CD pipeline with GitHub Actions
- ✅ Follow Azure deployment best practices

## ⏱️ Challenge Duration
**90 minutes total**
- 15 minutes: Setup and team formation
- 60 minutes: Main challenge implementation
- 15 minutes: Presentation and judging

## 🛠️ Required Tools & Extensions
Ensure you have installed:
- 🤖 **GitHub Copilot** (with agent mode enabled)
- 🔷 **GitHub Copilot for Azure** extension
- 🏗️ **Terraform** extension for VS Code
- ☁️ **Azure CLI** authenticated
- 📝 **YAML** extension for GitHub Actions

## 🎮 Challenge Setup

### Team Formation (5 minutes)
- Form teams of 2-3 people
- Choose a team name with an Azure theme (e.g., "Cloud Ninjas", "Bicep Warriors")
- Designate roles: Terraform Lead, CI/CD Specialist, Azure Expert

### Repository Setup (10 minutes)
1. Fork the challenge repository
2. Enable GitHub Copilot for your repository
3. Verify Azure extension is active

## 🏁 Challenge Mission

### 🎯 Primary Goal
Deploy a **secure, scalable web application** on Azure using:
- App Service with custom domain
- Azure SQL Database with failover
- Application Insights for monitoring
- Azure Key Vault for secrets
- CDN for static content

### 📋 Challenge Requirements

#### Infrastructure Requirements (40 points)
- [ ] Use GitHub Copilot agent mode (@workspace) to analyze and plan infrastructure
- [ ] Create modular Terraform structure
- [ ] Implement proper resource naming conventions
- [ ] Add comprehensive tags for cost management
- [ ] Include security best practices (NSGs, encryption, etc.)

#### CI/CD Pipeline Requirements (30 points)
- [ ] GitHub Actions workflow using Copilot generation
- [ ] Terraform plan and apply stages
- [ ] Azure authentication with OIDC
- [ ] Environment-specific deployments (dev, prod)
- [ ] Automated testing and validation

#### Azure Extension Usage (20 points)
- [ ] Use @azure agent for Azure-specific guidance
- [ ] Generate Azure CLI commands for setup
- [ ] Get architectural recommendations
- [ ] Implement monitoring and alerting

#### Code Quality (10 points)
- [ ] Proper variable definitions and outputs
- [ ] Meaningful commit messages
- [ ] Documentation and comments
- [ ] Error handling and validation

## 🤖 Using GitHub Copilot Agent Mode

### Starting Your Challenge
Open VS Code and start with agent mode:

```
@workspace Can you help me analyze the current infrastructure requirements and create a plan for deploying a secure web application on Azure using Terraform?
```

### Key Agent Commands to Use
```
@workspace /explain - Understand existing code structure
@workspace /new - Create new infrastructure components
@workspace /fix - Debug and fix configuration issues
@azure /help - Get Azure-specific guidance
@azure /generate - Generate Azure CLI commands
@azure /architecture - Get architectural recommendations
```

## 💡 Challenge Hints & Tips

### 🎯 Effective Agent Prompts
Use these patterns with @workspace:
```
@workspace Create a Terraform module for Azure App Service with these requirements: [list requirements]
@workspace Review my infrastructure code and suggest security improvements
@workspace Generate a GitHub Actions workflow for multi-environment deployment
@workspace Help me troubleshoot this Terraform state issue
```

### 🔷 Azure Extension Usage
```
@azure What are the best practices for App Service deployment?
@azure Generate Azure CLI commands to create service principal for GitHub Actions
@azure How should I configure monitoring for this web application?
@azure What security configurations should I implement?
```

### 🏗️ Terraform Best Practices
- Use @workspace to generate provider configurations
- Ask for module structure recommendations
- Get help with variable validation
- Generate comprehensive outputs

## 📊 Challenge Scoring

### Scoring Matrix
| Category | Excellent (100%) | Good (75%) | Needs Work (50%) | Incomplete (25%) |
|----------|------------------|------------|------------------|------------------|
| **Agent Mode Usage** | Extensive use of @workspace for all tasks | Good use for major tasks | Limited usage | Minimal usage |
| **Azure Extension** | @azure used for guidance and commands | Used for some Azure tasks | Basic usage | Not used |
| **Infrastructure Quality** | Secure, scalable, well-documented | Good structure, some issues | Basic functionality | Incomplete |
| **CI/CD Pipeline** | Full automation with testing | Good pipeline, minor issues | Basic pipeline | Incomplete |
| **Code Quality** | Excellent structure and docs | Good quality | Adequate | Poor |

### Bonus Points (5 points each)
- 🎨 Creative use of Copilot agents
- 🔒 Advanced security implementations
- 📈 Comprehensive monitoring setup
- 🚀 Performance optimizations
- 🏗️ Innovative infrastructure patterns

## 🎯 Challenge Milestones

### Milestone 1: Infrastructure Planning (15 minutes)
- [ ] Use @workspace to analyze requirements
- [ ] Create Terraform module structure
- [ ] Generate provider and variable configurations
- [ ] Get Azure extension recommendations

### Milestone 2: Core Infrastructure (25 minutes)
- [ ] Deploy App Service and SQL Database
- [ ] Configure networking and security
- [ ] Implement Key Vault integration
- [ ] Add monitoring with Application Insights

### Milestone 3: CI/CD Pipeline (15 minutes)
- [ ] Generate GitHub Actions workflow
- [ ] Configure Azure authentication
- [ ] Add testing and validation stages
- [ ] Test deployment pipeline

### Milestone 4: Final Polish (5 minutes)
- [ ] Add documentation and comments
- [ ] Verify all requirements met
- [ ] Prepare presentation

## 🎤 Presentation Guidelines

### Each team gets 3 minutes to present:
1. **Demo your deployment** (1 minute)
2. **Show Copilot agent usage** (1 minute)
3. **Highlight unique features** (1 minute)

### Judging Criteria:
- Functionality and completeness
- Creative use of Copilot agents
- Code quality and best practices
- Presentation clarity

## 🏆 Challenge Prizes

### 🥇 First Place: "Azure Architects"
- GitHub Copilot swag pack
- Azure credits
- Certificate of completion

### 🥈 Second Place: "Cloud Innovators"
- GitHub Copilot merchandise
- Azure credits

### 🥉 Third Place: "Terraform Masters"
- GitHub Copilot stickers
- Digital certificates

### 🎖️ Special Awards:
- **Best Use of Agent Mode** - Most creative @workspace usage
- **Security Champion** - Best security implementation
- **Innovation Award** - Most unique solution

## 🚨 Challenge Rules

### Do's ✅
- Use GitHub Copilot agent mode extensively
- Leverage Azure extension for guidance
- Collaborate within your team
- Ask instructors for clarification
- Help other teams if you finish early

### Don'ts ❌
- Copy code from other teams
- Use pre-written infrastructure code
- Skip security best practices
- Ignore the agent mode requirement
- Leave team members behind

## 📁 Challenge Starter Files

The challenge repository includes:
```
challenge-starter/
├── .github/
│   └── workflows/
│       └── template.yml
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   └── modules/
│       └── README.md
├── docs/
│   ├── requirements.md
│   └── architecture.md
└── scripts/
    └── setup.sh
```

## 🔗 Quick Reference

### Agent Commands Cheat Sheet
```bash
# Workspace agent
@workspace /explain <file>   # Explain code
@workspace /new <feature>    # Create new feature
@workspace /fix <issue>      # Fix problems
@workspace /tests           # Generate tests

# Azure agent
@azure /help                # Get help
@azure /generate <command>  # Generate CLI commands
@azure /architecture       # Architecture advice
@azure /best-practices     # Best practices
```

## 📝 Challenge Retrospective

After the challenge, teams will:
1. 🎯 Reflect on agent mode effectiveness
2. 📊 Share productivity improvements
3. 🔄 Discuss what worked well
4. 💡 Identify areas for improvement
5. 🚀 Plan next steps for adoption

## 🎉 Challenge Completion

### Success Metrics
- [ ] Infrastructure deployed successfully
- [ ] CI/CD pipeline functional
- [ ] Security best practices implemented
- [ ] Copilot agents used effectively
- [ ] Team collaboration successful

### Next Steps
- Apply these techniques to real projects
- Continue exploring agent mode capabilities
- Share learnings with your organization
- Contribute to the workshop feedback

---

**Ready to revolutionize your infrastructure deployment with AI? Let's begin the challenge! 🚀**

*Remember: The goal is not just to deploy infrastructure, but to discover how GitHub Copilot agents can transform your development workflow!*
