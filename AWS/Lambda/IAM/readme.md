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

## 🔁 IAM USERS vs GROUPS vs ROLES

| Feature           | IAM User          | IAM Group           | IAM Role                    |
| ----------------- | ----------------- | ------------------- | --------------------------- |
| Represents        | Person / App      | Collection of users | AWS service / external user |
| Login Credentials | ✅ Yes             | ❌ No                | ❌ No                        |
| Permissions       | Directly attached | Attached to group   | Attached to role            |
| Access Type       | Long-term         | Long-term           | Temporary                   |
| Common Use        | Admin, Developer  | Team management     | EC2, Lambda, Cross-account  |
