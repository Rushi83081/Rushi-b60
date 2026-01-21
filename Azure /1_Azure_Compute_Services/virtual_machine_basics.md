# 1.Virtual Machine (VM)

A Virtual Machine (VM) is a server created in the Azure cloud.

- A VM in Azure is similar to **EC2 in AWS**.
- It is used to create one server in the cloud.
- VMs are good for:
  - Testing
  - Learning
  - Small applications

### Example
- Creating an Ubuntu machine
- Hosting a simple website

Azure automatically manages required resources like network and storage when creating a VM.

---

# 2.Virtual Machine Scale Set (VMSS)

Virtual Machine Scale Set (VMSS) is used to run **multiple VMs together**.

- Azure automatically adds or removes VMs based on traffic.
- Useful for applications with many users.
- Best for big websites and large applications.
- It works like **Auto Scaling in AWS**.

### Key Points
- All VMs are identical
- Scaling happens automatically
- Helps handle high traffic

---

# VM Presets

VM Presets are **ready-made Virtual Machines** provided by Azure.

- These VMs already have predefined settings.
- Configuration is already chosen by Azure.
- Helps save time when you are not sure what to select.
- Useful for quick setup.

Presets are good for beginners and fast deployments.

---

# Hybrid and High Volume Solutions

Hybrid and high-volume solutions are mainly used by **large companies**.

- Helps connect **on-premises servers** to Azure cloud.
- Used when companies want to move servers to Azure.
- Makes migration from on-prem to cloud easier.

### Example
A company wants to move 50 servers to Azure.
Hybrid solutions help in connecting and migrating those servers easily.

