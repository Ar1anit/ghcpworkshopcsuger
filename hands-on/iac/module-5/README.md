# Module 5: CI/CD Integration 🔄

## 📚 Learning Objectives
By the end of this module, participants will:
- Create GitHub Actions workflows for IaC deployment
- Implement automated testing and validation pipelines
- Set up approval gates and deployment strategies
- Monitor and troubleshoot infrastructure deployments

## ⏱️ Duration
75 minutes

## 🎯 Module Content

### 5.1 GitHub Actions for IaC (25 minutes)
**Instructor Demo:**
Generate complete CI/CD workflows:

```yaml
# Create GitHub Actions workflow for Terraform
# Include plan, validate, and apply stages
# Add security scanning and compliance checks
```

**Workflow Components:**
- Terraform plan and apply
- Azure authentication
- State management
- Artifact handling

### 5.2 Automated Testing Pipeline (20 minutes)
**Guided Exercise:**
Create comprehensive testing workflows:

```yaml
# Add Terratest integration to GitHub Actions
# Include security scanning with Checkov
# Add infrastructure validation tests
```

### 5.3 Deployment Strategies (15 minutes)
**Hands-on Activity:**
Implement different deployment patterns:
- Blue-green deployments
- Canary releases
- Rolling updates
- Feature flags for infrastructure

### 5.4 Monitoring and Observability (15 minutes)
**Instructor Notes:**
- Deployment monitoring
- Infrastructure drift detection
- Cost monitoring and alerts
- Performance tracking

## 🛠️ Hands-On Exercises

### Exercise 5.1: Complete CI/CD Pipeline
**Time:** 40 minutes

**Instructions:**
1. Create a full GitHub Actions workflow
2. Include all testing and validation stages
3. Add approval gates for production

**Pipeline Stages:**
1. Code checkout and setup
2. Terraform validation and security scan
3. Plan generation and review
4. Manual approval gate
5. Infrastructure deployment
6. Post-deployment testing

### Exercise 5.2: Multi-Environment Deployment
**Time:** 25 minutes

**Instructions:**
1. Create workflows for dev, staging, and production
2. Implement environment-specific configurations
3. Add automated promotion between environments

### Exercise 5.3: Monitoring and Alerting
**Time:** 10 minutes

**Instructions:**
1. Set up deployment monitoring
2. Create alerts for infrastructure changes
3. Implement cost monitoring

## 📁 Exercise Files
```
.github/
└── workflows/
    ├── terraform-plan.yml
    ├── terraform-apply.yml
    ├── infrastructure-test.yml
    └── security-scan.yml
environments/
├── dev/
│   ├── terraform.tfvars
│   └── backend.tf
├── staging/
│   ├── terraform.tfvars
│   └── backend.tf
└── prod/
    ├── terraform.tfvars
    └── backend.tf
tests/
├── unit/
├── integration/
└── compliance/
scripts/
├── setup-backend.sh
├── deploy.sh
└── cleanup.sh
```

## 🔄 Sample GitHub Actions Workflow
```yaml
name: 'Infrastructure Deploy'
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  terraform:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Setup Terraform
      uses: hashicorp/setup-terraform@v2
    - name: Azure Login
      uses: azure/login@v1
      with:
        creds: ${{ secrets.AZURE_CREDENTIALS }}
    # Add more steps using Copilot...
```

## 📊 Deployment Metrics
Track these key metrics:
- Deployment success rate
- Mean time to deployment
- Infrastructure drift frequency
- Cost per deployment
- Security scan results

## 🚨 Best Practices
- Always run plan before apply
- Use remote state with locking
- Implement proper secret management
- Monitor infrastructure costs
- Set up proper alerting and notifications

## 📝 Key Takeaways
- Automation reduces human error and increases consistency
- Proper testing prevents production issues
- Monitoring is essential for operational success
- GitHub Copilot can generate complex CI/CD workflows

## 🎉 Workshop Completion
Congratulations! You've completed all modules of the IaC Workshop with GitHub Copilot.

## 🔗 Additional Resources
- [GitHub Actions Documentation](https://docs.github.com/actions)
- [Terraform Cloud](https://cloud.hashicorp.com/products/terraform)
- [Azure DevOps](https://azure.microsoft.com/services/devops/)
