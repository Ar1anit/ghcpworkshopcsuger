# IaC Workshop with GitHub Copilot - Instructor Guide 👨‍🏫

## 📋 Workshop Overview
**Duration:** 5.5 hours (including breaks)  
**Format:** Hands-on workshop with guided exercises  
**Audience:** Developers, DevOps engineers, Cloud architects  
**Group Size:** 8-20 participants (ideal: 12-15)

## 🎯 Workshop Flow
```
09:00-09:45  Module 1: Getting Started (45 min)
09:45-10:00  Break (15 min)
10:00-11:00  Module 2: Terraform Development (60 min)
11:00-11:15  Break (15 min)
11:15-12:30  Module 3: Azure Templates (75 min)
12:30-13:30  Lunch Break (60 min)
13:30-15:00  Module 4: Advanced Patterns (90 min)
15:00-15:15  Break (15 min)
15:15-16:30  Module 5: CI/CD Integration (75 min)
16:30-17:00  Wrap-up and Q&A (30 min)
```

## 🛠️ Pre-Workshop Setup

### Required Tools Check
Before starting, verify all participants have:
- [ ] GitHub Copilot subscription active
- [ ] VS Code with Copilot extension
- [ ] Azure CLI installed and configured
- [ ] Terraform CLI (latest version)
- [ ] Git configured with GitHub access
- [ ] Azure subscription with contributor access

### Environment Preparation
```bash
# Create workshop resource group
az group create --name rg-iac-workshop --location eastus

# Verify permissions
az role assignment list --assignee $(az account show --query user.name -o tsv)
```

## 📚 Module-by-Module Instructions

### Module 1: Getting Started (45 minutes)
**Instructor Focus:**
- Emphasize the importance of good prompting
- Show live coding with Copilot
- Address common setup issues immediately

**Common Issues:**
- Copilot not suggesting: Check extension status
- Azure CLI not authenticated: Run `az login`
- Terraform not found: Verify PATH configuration

**Key Demo Points:**
1. Show Copilot generating basic Terraform
2. Demonstrate comment-driven development
3. Explain when to accept vs. modify suggestions

### Module 2: Terraform Development (60 minutes)
**Instructor Focus:**
- Emphasize code organization principles
- Show module creation best practices
- Demonstrate variable validation

**Teaching Tips:**
- Walk through the module creation step-by-step
- Show how Copilot understands context between files
- Emphasize the importance of meaningful variable descriptions

**Time Management:**
- 20 min: Resource generation demo
- 20 min: Module creation exercise
- 15 min: Variables and outputs
- 5 min: Q&A and troubleshooting

### Module 3: Azure Templates (75 minutes)
**Instructor Focus:**
- Compare ARM vs. Bicep clearly
- Show template conversion techniques
- Emphasize Azure-specific best practices

**Demo Sequence:**
1. Generate ARM template with Copilot (10 min)
2. Convert to Bicep (10 min)
3. Add modules and parameters (15 min)
4. Guide through exercises (40 min)

**Common Questions:**
- "When to use ARM vs. Bicep?" → Always prefer Bicep for new projects
- "How to handle existing ARM templates?" → Convert gradually
- "What about Terraform vs. Bicep?" → Explain use cases for each

### Module 4: Advanced Patterns (90 minutes)
**Instructor Focus:**
- Security-first approach
- Real-world architecture patterns
- Testing methodologies

**Critical Points:**
- Always review generated security configurations
- Explain the hub-and-spoke pattern clearly
- Show how to test infrastructure code

**Exercise Monitoring:**
- Walk around during hands-on exercises
- Help with complex networking concepts
- Ensure security best practices are followed

### Module 5: CI/CD Integration (75 minutes)
**Instructor Focus:**
- GitHub Actions workflow creation
- Secret management best practices
- Deployment strategies

**Live Demo Must-Haves:**
1. Complete workflow creation with Copilot
2. Show secret configuration in GitHub
3. Demonstrate plan vs. apply workflow

## 🎯 Success Criteria

### Participant Outcomes
By workshop end, participants should be able to:
- [ ] Generate infrastructure code 3x faster with Copilot
- [ ] Create secure, well-structured IaC templates
- [ ] Implement CI/CD pipelines for infrastructure
- [ ] Apply security and testing best practices

### Knowledge Check Questions
**Module 1:**
- How do you write effective prompts for Copilot?
- What are the key setup requirements?

**Module 2:**
- When should you create a Terraform module?
- How do you organize Terraform code effectively?

**Module 3:**
- What are the advantages of Bicep over ARM JSON?
- How do you handle parameters in Azure templates?

**Module 4:**
- What security considerations are important for IaC?
- How do you test infrastructure code?

**Module 5:**
- What are the key stages in an IaC pipeline?
- How do you handle secrets in GitHub Actions?

## 🚨 Troubleshooting Guide

### Common Issues and Solutions

**Copilot Not Working:**
```bash
# Check extension status
code --list-extensions | grep copilot

# Restart VS Code
# Check GitHub Copilot subscription status
```

**Azure Authentication Issues:**
```bash
# Clear and re-authenticate
az logout
az login
az account show
```

**Terraform State Issues:**
```bash
# Initialize backend
terraform init
# Force unlock if needed
terraform force-unlock <lock-id>
```

**GitHub Actions Failures:**
- Check Azure credentials in secrets
- Verify Terraform syntax
- Review action logs carefully

## 📊 Workshop Metrics

### Track These During Workshop
- Number of participants completing each module
- Common questions and issues
- Time spent on each exercise
- Participant feedback on difficulty

### Post-Workshop Survey Questions
1. Rate the workshop content (1-5)
2. How confident are you using Copilot for IaC? (1-5)
3. What was the most valuable part?
4. What would you improve?
5. Would you recommend this workshop?

## 🎯 Tips for Success

### Instructor Best Practices
- **Start with energy** - Enthusiasm is contagious
- **Show, don't just tell** - Live coding is essential
- **Manage time strictly** - Use timers for exercises
- **Encourage questions** - Create a safe learning environment
- **Share real experiences** - Use concrete examples from your work

### Managing Different Skill Levels
- **Beginners:** Pair with experienced participants
- **Advanced:** Give them additional challenges
- **Mixed groups:** Use breakout rooms for different paces

### Handling Technical Issues
- **Have backup plans** - Pre-generated code examples
- **Use chat for help** - Slack/Teams for quick questions
- **Buddy system** - Participants help each other
- **Time buffers** - Build in extra time for troubleshooting

## 📝 Post-Workshop Actions

### Immediate Follow-up (Day 1)
- [ ] Send thank you email with resources
- [ ] Share workshop materials and recordings
- [ ] Collect detailed feedback survey
- [ ] Schedule optional Q&A session

### One Week Follow-up
- [ ] Check on participant progress
- [ ] Answer any additional questions
- [ ] Share advanced resources and tutorials

### One Month Follow-up
- [ ] Measure adoption in participants' projects
- [ ] Collect success stories and case studies
- [ ] Plan advanced workshop sessions

## 🔗 Additional Resources for Instructors
- [GitHub Copilot Training Materials](https://github.com/features/copilot)
- [Azure Architecture Center](https://docs.microsoft.com/azure/architecture/)
- [Terraform Best Practices](https://www.terraform.io/docs/cloud/guides/recommended-practices/)
- [Infrastructure Testing Guide](https://terratest.gruntwork.io/)

---
**Remember:** The goal is not just to teach tools, but to change how participants think about infrastructure development with AI assistance! 🚀
