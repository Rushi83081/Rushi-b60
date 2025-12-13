# 🌍 **DevOps — Terraform**

## 🧩 **Overview**

Terraform is an **open‑source Infrastructure as Code (IaC)** tool developed by **HashiCorp**. It enables you to **define, provision, and manage infrastructure** across multiple cloud providers using **HCL (HashiCorp Configuration Language)**.

**Terraform is used to automate infrastructure using code**

---

## ⚙️ **Why Use Terraform?**

✨ **Automation** — Fully automated and repeatable infrastructure deployments.

🌐 **Multi‑Cloud Support** — Works with AWS, Azure, GCP, Kubernetes, and many more.

🔁 **Consistency** — Ensures reproducible and reliable environments across teams.

📈 **Scalability** — Easily manage small to enterprise‑level infrastructure.

🧠 **Version Control** — Track every infrastructure change using Git.

---

## 🏗️ **Core Concepts**

| Concept          | Description                                                       |
| ---------------- | ----------------------------------------------------------------- |
| **Provider**     | Plugin that lets Terraform manage resources (e.g., AWS, Azure).   |
| **Resource**     | The component of infrastructure to manage (like an EC2 instance). |
| **Module**       | Reusable collection of Terraform configurations.                  |
| **State File**   | Tracks the real-world resources created by Terraform.             |
| **Plan & Apply** | Stages of previewing and deploying infrastructure changes.        |

---

## 📦 **Basic Workflow**

1️⃣ **Write** → Define infrastructure in `.tf` files.

2️⃣ **Init** → `terraform init` to download provider plugins.

3️⃣ **Validate** → `terraform validate` to verify configuration syntax.

4️⃣ **Plan** → `terraform plan` to preview changes.

5️⃣ **Apply** → `terraform apply` to create/update infrastructure.

6️⃣ **Destroy** → `terraform destroy` to remove resources.

---

## 🗂️ **Terraform Project Structure**

```
📁 terraform/
│── main.tf
│── provider.tf
│
└── modules/
    ├── vpc/
    │   ├── vpc.tf
    │   ├── variableVpc.tf
    │   └── output.tf
    │
    └── ec2/
        ├── ec2.tf
        ├── variableEc2.tf
       
```

