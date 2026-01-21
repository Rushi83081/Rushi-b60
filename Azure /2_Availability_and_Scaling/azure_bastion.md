# Azure Bastion

1. Azure Bastion is a secure way to connect to Azure VMs.
2. Azure Bastion is a **jump server** provided by Azure.

- No need for public IP
- No need to open SSH (22) or RDP (3389) ports
- Connection happens through Azure Portal

### Why Bastion?
Opening SSH or RDP exposes VM to the internet and is a security risk.
Azure Bastion removes this risk.
