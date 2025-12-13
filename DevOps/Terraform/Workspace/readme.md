# 🌐 Terraform Workspace 

Manage multiple environments (dev, test, prod) using **Terraform Workspaces**. 

---

## 🚀 What Are Terraform Workspaces?

Terraform workspaces allow you to maintain multiple state files within the same configuration. This is helpful for managing different environments without duplicating code.

---

## 🔢 Essential Workspace Commands

### **1️⃣ Create a New Workspace**

```bash
terraform workspace new <name>
```

**Example:**

```bash
terraform workspace new prod
```

**Explanation:** Creates a new workspace named **prod**. Useful when starting a new environment.

---

### **2️⃣ Select an Existing Workspace**

```bash
terraform workspace select <name>
```

**Example:**

```bash
terraform workspace select default
```

**Explanation:** Switches to an existing workspace. All future Terraform commands (`plan`, `apply`, etc.) will now apply to this workspace.

---

### **3️⃣ List All Workspaces**

```bash
terraform workspace list
```

**Explanation:** Lists all available workspaces and marks the active one with an asterisk `*`.

---

### **4️⃣ Show the Active Workspace**

```bash
terraform workspace show
```

**Explanation:** Displays the name of the currently selected workspace.

---

## 📌 When Should You Use Workspaces?

Use workspaces for:

* 🔹 Dev / Test / Prod separation
* 🔹 Isolated Terraform state files
* 🔹 Avoiding duplicate Terraform code across environments

Avoid workspaces when:

* 🔸 You need separate backend configurations
* 🔸 You manage infra across multiple regions/accounts (use separate folders instead)

---
