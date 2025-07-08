# Module 4: Advanced IaC Patterns 🚀

## 📚 Learning Objectives
By the end of this module, participants will:
- Generate complex infrastructure patterns using Copilot
- Implement security and compliance best practices
- Create testable infrastructure code
- Use advanced Terraform and Azure features

## ⏱️ Duration
90 minutes

## 🎯 Module Content

### 4.1 Complex Infrastructure Patterns (30 minutes)
**Instructor Demo:**
Generate advanced patterns:

```hcl
# Create a hub-and-spoke network architecture
# Include Azure Firewall, VPN Gateway, and peering
# Add monitoring and logging for all components
```

**Advanced Patterns to Cover:**
- Hub and spoke networking
- Multi-region deployments
- Disaster recovery configurations
- Microservices infrastructure

### 4.2 Security and Compliance (25 minutes)
**Guided Exercise:**
Use Copilot for security-first infrastructure:

```hcl
# Create infrastructure with zero-trust principles
# Include Azure Policy assignments
# Add Azure Security Center configurations
# Implement proper RBAC and access controls
```

**Security Focus Areas:**
- Identity and access management
- Network security and segmentation
- Data encryption and key management
- Compliance and governance

### 4.3 Infrastructure Testing (20 minutes)
**Hands-on Activity:**
Generate test code with Copilot:

```go
// Create Terratest code for infrastructure validation
// Include unit tests for Terraform modules
// Add integration tests for deployed resources
```

### 4.4 Advanced Terraform Features (15 minutes)
**Instructor Notes:**
- Dynamic blocks and for_each loops
- Conditional resource creation
- Custom providers and data sources
- State management best practices

## 🛠️ Hands-On Exercises

### Exercise 4.1: Hub-and-Spoke Architecture
**Time:** 45 minutes

**Instructions:**
1. Create a complete hub-and-spoke network
2. Include all security components
3. Use Copilot for complex configurations

**Components to Include:**
- Hub VNet with shared services
- Multiple spoke VNets
- Azure Firewall with rules
- VPN Gateway configuration
- Network monitoring

### Exercise 4.2: Security-First Web Application
**Time:** 30 minutes

**Instructions:**
1. Generate a web application with security hardening
2. Include all compliance requirements
3. Add monitoring and alerting

**Security Requirements:**
- Web Application Firewall
- DDoS protection
- SSL/TLS termination
- Database encryption
- Key Vault integration

### Exercise 4.3: Infrastructure Testing
**Time:** 15 minutes

**Instructions:**
1. Create test files for your infrastructure
2. Use Copilot for test generation
3. Run basic validation tests

## 📁 Exercise Files
```
exercises/
├── hub-spoke-architecture/
│   ├── hub/
│   │   ├── main.tf
│   │   ├── firewall.tf
│   │   └── gateway.tf
│   ├── spoke/
│   │   ├── main.tf
│   │   └── workload.tf
│   └── tests/
│       └── infrastructure_test.go
├── security-hardened-app/
│   ├── infrastructure/
│   ├── security/
│   └── monitoring/
└── examples/
    ├── multi-region/
    ├── disaster-recovery/
    └── compliance-templates/
```

## 🔒 Security Checklist
- [ ] Network segmentation implemented
- [ ] Encryption at rest and in transit
- [ ] Proper RBAC configuration
- [ ] Security monitoring enabled
- [ ] Compliance policies applied
- [ ] Backup and disaster recovery configured

## 📝 Key Takeaways
- Security should be built into infrastructure from the start
- Complex patterns can be generated efficiently with Copilot
- Always test infrastructure code before production deployment
- Documentation and comments improve Copilot suggestions

## 🔗 Next Module
[Module 5: CI/CD Integration](../module-5/README.md)
