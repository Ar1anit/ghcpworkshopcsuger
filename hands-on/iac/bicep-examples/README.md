# Bicep Examples

This directory is your workspace for the Bicep portion of the workshop.

## Exercise Structure

Suggested file organization:
```
bicep-examples/
├── main.bicep              # Main template
├── parameters.json         # Parameter file
└── modules/               # Reusable modules
    ├── storage.bicep
    ├── webapp.bicep
    └── network.bicep
```

## Getting Started

1. **Verify Bicep installation**:
   ```bash
   az bicep version
   ```

2. **Create a resource group** (if needed):
   ```bash
   az group create --name rg-workshop --location eastus
   ```

3. **Start with a comment** in your `.bicep` file and let Copilot help:
   ```bicep
   // Create a storage account with secure defaults
   ```

4. **Build your template** (optional - checks for errors):
   ```bash
   az bicep build --file main.bicep
   ```

5. **Deploy your template**:
   ```bash
   az deployment group create \
     --resource-group rg-workshop \
     --template-file main.bicep
   ```

## Using Parameters

Deploy with a parameter file:
```bash
az deployment group create \
  --resource-group rg-workshop \
  --template-file main.bicep \
  --parameters parameters.json
```

Or pass parameters inline:
```bash
az deployment group create \
  --resource-group rg-workshop \
  --template-file main.bicep \
  --parameters location=eastus envName=dev
```

## Copilot Tips

- Use descriptive comments for each resource
- Request modules for reusable components
- Ask for parameter decorations (@description, @minLength, etc.)
- Include outputs for important resource properties

## Validate Before Deploy

```bash
az deployment group validate \
  --resource-group rg-workshop \
  --template-file main.bicep
```

## Clean Up

Delete the resource group when done:
```bash
az group delete --name rg-workshop --yes
```

## What-If Analysis

Preview changes before deploying:
```bash
az deployment group what-if \
  --resource-group rg-workshop \
  --template-file main.bicep
```
