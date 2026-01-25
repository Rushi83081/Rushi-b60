# 🔐 AWS IAM (Identity and Access Management)

**AWS Identity and Access Management (IAM)** is a **global AWS service** that helps you securely control access to AWS resources.

> 👉 IAM answers three key questions in AWS:  
> **WHO** can access **WHAT** and **HOW**

---

## 📌 Why IAM is Needed?

IAM is essential for managing security and access in AWS.

✅ Secure AWS resources  
✅ Control access using permissions  
✅ Follow the **Principle of Least Privilege**  
✅ Avoid sharing the **root account**  
✅ Manage users and services safely  

---

## 🧱 IAM Core Components

### 1️⃣ IAM Users
- Represents a **person or application**
- Has **username & password** or **access keys**
- Used for **long-term access**

---

### 2️⃣ IAM Groups
- Collection of **IAM users**
- Permissions are assigned to the **group**
- Users **inherit permissions** from the group

---

### 3️⃣ IAM Roles
- Used to grant **temporary permissions**
- **No username or password**
- Commonly used with:
  - EC2
  - Lambda
  - EKS
  - Cross-account access

---

### 4️⃣ IAM Policies
- JSON document that defines **permissions**
- Attached to **users, groups, or roles**
- Controls **Allow** or **Deny** actions

---

## 📄 AWS IAM Policy Types

IAM policies define what actions are **allowed or denied** on AWS resources.  
They are written in **JSON format** and attached to IAM identities.

---

## 🧱 Types of IAM Policies

AWS IAM supports **three main policy types**:

### 1️⃣ Managed Policies
Standalone policies that can be attached to multiple IAM identities.

#### 🔹 Characteristics
- Created and managed separately  
- Reusable across users, groups, and roles  
- Easy to update and maintain  

#### 🔹 Types of Managed Policies
- **AWS Managed Policies** – Created and maintained by AWS  
- **Customer Managed Policies** – Created and managed by users  

---

### 2️⃣ Inline Policies
Policies directly embedded into a **single user, group, or role**.

#### 🔹 Characteristics
- Tightly coupled to one identity  
- ❌ Not reusable  
- Deleted automatically when the identity is deleted  

---

### 3️⃣ Permissions Boundary (Advanced)
Permissions boundaries define the **maximum permissions** an IAM entity can have.

#### 🔹 Characteristics
- Acts as a **permission limit**
- Used with **users or roles**
- Commonly used in **large organizations**

---

## 🔁 Differences

### 🔐 IAM Users vs Groups vs Roles

| Feature           | IAM User          | IAM Group           | IAM Role                    |
|-------------------|------------------|---------------------|-----------------------------|
| Represents        | Person / App     | Collection of users | AWS service / external user |
| Login Credentials | ✅ Yes            | ❌ No                | ❌ No                        |
| Permissions       | Directly attached| Attached to group   | Attached to role            |
| Access Type       | Long-term        | Long-term           | Temporary                   |
| Common Use        | Admin, Developer | Team management     | EC2, Lambda, Cross-account  |

---

### 📜 IAM Policies vs Roles

| Feature     | IAM Policy                  | IAM Role                    |
|------------|-----------------------------|-----------------------------|
| What it is | Permission document         | Identity with permissions   |
| Purpose    | Defines **what is allowed** | Grants **temporary access** |
| Used By    | Users, Groups, Roles        | AWS services / users        |
| Credentials| ❌ No                        | ❌ No                        |
| Example    | Allow S3 access             | EC2 accessing S3            |

---

### 🆚 Inline Policy vs Managed Policy

| Feature         | Inline Policy    | Managed Policy       |
|-----------------|------------------|----------------------|
| Attached To     | Single identity  | Multiple identities  |
| Reusability     | ❌ No             | ✅ Yes                |
| AWS Recommended | ❌ No             | ✅ Yes                |
| Management      | Harder           | Easier               |

---

✨ **Tip:** Always use **IAM roles** for AWS services and follow the **least privilege principle** for better security.
