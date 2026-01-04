# 🧩 Overview

**Git** is a distributed version control system (DVCS) that helps teams track changes, collaborate, and manage code efficiently.

# ⚙️ Why Git?

  **🧑‍🤝‍🧑 Collaboration**: Work together without overwriting code.

  **🔁 Version History**: Track every change.

  **🕒 Rollback**: Easily revert to previous versions.

  **🧱 Branching & Merging**: Isolate and combine features seamlessly.

  **🌍 Open Source & Universal**: Works with GitHub, GitLab, Bitbucket, etc.

# 🏗️ Core Concepts

| Concept               | Description                               |
| --------------------- | ----------------------------------------- |
| **Repository (Repo)** | Project storage for all versions.         |
| **Commit**            | A snapshot of your code changes.          |
| **Branch**            | A separate line of development.           |
| **Merge**             | Combines changes from branches.           |
| **Remote**            | A repository hosted online (like GitHub). |

## Git Architecture
```
+---------------------+
|  Working Directory  |
|  (Your Project)     |
+----------+----------+
           |
           | git add
           ▼
+---------------------+
|    Staging Area     |
|   (Index / Cache)   |
+----------+----------+
           |
           | git commit
           ▼
+---------------------+
|  Local Repository   |
|   (.git Directory)  |
+----------+----------+
           |
           | git push
           ▼
+---------------------+
|  Remote Repository  |
| (GitHub / GitLab)   |
+---------------------+
```

# 🛠️ Basic Commands

# Working Directory
```bash
git status
```
# Initialize repository
```bash
git init
```
# Add file to staging 
```bash
git add (filename)
```
# Add all files
```bash
git add .
```
# Commit changes
```bash
git commit -m "Mesasge"
```
# Create and switch branches
```bash
git branch feature-xyz
git checkout feature-xyz
```
# Push to remote
```bash
git push origin main
```
# Pull latest changes
```bash
git pull origin main
```
# View log
```bash
git log --oneline
```
