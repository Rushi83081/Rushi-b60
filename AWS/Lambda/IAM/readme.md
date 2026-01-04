# 🔐 AWS IAM (Identity and Access Management)

- **AWS IAM** is a global service that allows you to manage users, permissions, and access to AWS services securely.

👉 IAM answers WHO can access WHAT and HOW in AWS.

## 📌 Why IAM is Needed?

* Secure AWS resources

* Control access using permissions

* Follow least privilege principle

* Avoid sharing root account

  ---

## 🧱 IAM Core Components

### 1️⃣ IAM Users

* Represents a person or application

* Has username + password / access keys

* Used for long-term access

### 2️⃣ IAM Groups

* Collection of IAM users

* Permissions are assigned to group

* Users inherit group permissions

### 3️⃣ IAM Roles

* Used to grant temporary permissions

* No username or password

* Commonly used with EC2, Lambda, EKS

### 4️⃣ IAM Policies

* JSON document that defines permissions

* Attached to users, groups, or roles

* Controls Allow / Deny actions

  📄 AWS IAM Policy Types

AWS IAM policies define what actions are allowed or denied on AWS resources.
Policies are written in JSON and are attached to users, groups, or roles.

## 🧱 Types of IAM Policies

AWS IAM supports three main policy types:

### 1️⃣ Managed Policies

- Managed policies are standalone policies that can be attached to multiple IAM identities.

🔹 Characteristics

- * Created and managed separately

- * Reusable across users, groups, and roles

- * Easy to update and maintain

### 🔹 Types of Managed Policies

- * AWS Managed Policies – Created by AWS

- * Customer Managed Policies – Created by users

### 2️⃣ Inline Policies

Inline policies are directly embedded into a single user, group, or role.

🔹 Characteristics

- * Tightly coupled to one identity

- * Cannot be reused

- * Deleted automatically when identity is deleted

### 3️⃣ Permissions Boundary (Advanced)

Permissions boundaries set the maximum permissions an IAM entity can have.

🔹 Characteristics

- * Acts as a permission limit

- * Used with users or roles

- * Common in large organizations

## Differences

## 🔁 IAM USERS vs GROUPS vs ROLES

| Feature           | IAM User          | IAM Group           | IAM Role                    |
| ----------------- | ----------------- | ------------------- | --------------------------- |
| Represents        | Person / App      | Collection of users | AWS service / external user |
| Login Credentials | ✅ Yes             | ❌ No                | ❌ No                        |
| Permissions       | Directly attached | Attached to group   | Attached to role            |
| Access Type       | Long-term         | Long-term           | Temporary                   |
| Common Use        | Admin, Developer  | Team management     | EC2, Lambda, Cross-account  |

## 🔁 IAM POLICIES vs ROLES

| Feature     | IAM Policy                  | IAM Role                    |
| ----------- | --------------------------- | --------------------------- |
| What it is  | Permission document         | Identity with permissions   |
| Purpose     | Defines **what is allowed** | Grants **temporary access** |
| Used By     | Users, Groups, Roles        | AWS services / users        |
| Credentials | ❌ No                        | ❌ No                        |
| Example     | Allow S3 access             | EC2 accessing S3            |

## 🔁 INLINE POLICY vs MANAGED POLICY

| Feature         | Inline Policy    | Managed Policy       |
| --------------- | ---------------- | -------------------- |
| Attached To     | Single user/role | Multiple users/roles |
| Reusability     | ❌ No             | ✅ Yes                |
| AWS Recommended | ❌ No             | ✅ Yes                |
| Management      | Harder           | Easier               |
