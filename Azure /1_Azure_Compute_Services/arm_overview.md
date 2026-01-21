# Azure Resource Manager (ARM)

ARM is the management layer of Azure.

It allows you to:
- Create resources
- Update resources
- Organize resources
- Delete resources

All resources are managed in a consistent way using ARM.

---

# ARM Components 

## 1.Resource Group
- A logical container for Azure resources.

## 2.Resource Provider
- A service that knows how to create a resource.

### Examples
- Virtual Machine → Microsoft.Compute
- Storage → Microsoft.Storage

## 3.ARM Template
- A JSON file
- Describes what resources to create

## 4.Deployment Engine
- Reads ARM templates
- Validates syntax
- Checks permissions
- Deploys resources

## 5.Dependencies
- Some resources depend on others
- Example: VM depends on VNet and storage
- ARM creates resources in the correct order automatically

---
