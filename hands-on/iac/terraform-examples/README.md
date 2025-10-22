# Terraform Examples

This directory is your workspace for the Terraform portion of the workshop.

## Exercise Structure

Create separate `.tf` files for each exercise or keep everything in `main.tf` - your choice!

Suggested file organization:
```
terraform-examples/
├── main.tf           # Main resources
├── variables.tf      # Variable definitions
├── outputs.tf        # Output values
├── providers.tf      # Provider configuration
└── terraform.tfvars  # Variable values (don't commit secrets!)
```

## Getting Started

1. **Initialize Terraform**:
   ```bash
   terraform init
   ```

2. **Start with a comment** in your `.tf` file and let Copilot help:
   ```hcl
   # Configure Azure provider with required features
   ```

3. **Validate your configuration**:
   ```bash
   terraform validate
   ```

4. **Plan your deployment**:
   ```bash
   terraform plan
   ```

5. **Apply when ready**:
   ```bash
   terraform apply
   ```

## Copilot Tips

- Write comments explaining your infrastructure intent
- Be specific about resource properties
- Ask for security best practices
- Request outputs for important values

## Clean Up

When you're done with exercises:
```bash
terraform destroy
```

This ensures you don't incur unnecessary Azure costs.
