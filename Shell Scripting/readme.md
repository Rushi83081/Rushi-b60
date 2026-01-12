# 🐚 Shell Scripting 

---

## 📌 1. Terminal vs Shell (📍)

### 🖥️ Terminal
- A **Terminal** is a **text-based interface**.
- It is used to type and run commands.
- Examples:
  - GNOME Terminal
  - iTerm
  - Windows Terminal

### 🧠 Shell
- A **Shell** is a **command interpreter**.
- It reads commands from the terminal and executes them.
- Acts as a **bridge between User and OS Kernel**.

---

## 📌 2. Types of Shell 🐧 (📍)

Common shells available in Linux/Unix:

- 🔹 **sh** – Bourne Shell  
- 🔹 **bash** – Bourne Again Shell (**Most Popular**)  
- 🔹 **zsh** – Z Shell  
- 🔹 **ksh** – Korn Shell  
- 🔹 **csh** – C Shell  

---

## 📌 3. `/etc/shells` 📂

- `/etc/shells` is a system file.
- It contains a **list of valid login shells**.
- The OS checks this file to know which shells are allowed.

---

## 📌 4. Shell Scripting ✍️ (📍)

- **Shell scripting** means writing commands in a file.
- These scripts are executed by a shell.
- Used for **automation tasks** like:
  - 📁 File handling
  - 💾 Backups
  - ⚙️ System administration
  - 📊 Monitoring

---

## 📌 5. Shebang Line (`#!`) ⭐

### ❓ What is Shebang?
- The **first line** of a shell script.
- Starts with `#!`
- Specifies **which shell should execute the script**.

### 🧾 Examples
```bash
#!/bin/bash
#!/bin/sh
```
---

## 🔍 Why Shebang is Used?

* Instructs the OS to use a specific command interpreter.

* Decides which shell will execute the script.

### 📝 Important Points

* '#' → Sharp

* '!' → Bang

* '#!' → Shebang

* Name comes from musical notation
___


## 📌 6. Create Your First Shell Script 🚀 

### ✏️ Step 1: Create a Script File (In LabEx)
```bash
vim 1.sh
```
🔔 Note: The .sh extension is not mandatory, but it is recommended for clarity.
___

### ✏️ Step 2: Write the Script
```
#!/bin/bash

echo "Hello World"
```
* #!/bin/bash → Shebang line (defines interpreter)

* echo → Used to print output on the terminal
___


## 📌 7. Give Execute Permission 🔐

Before running the script directly, give execute permission:
```
chmod u+x 1.sh
```
## OR
```
chmod 700 1.sh
```
* chmod → Change mode (permission)

* u+x → Adds execute permission to the user
___


## 📌 8. Run the Script ▶️

### ▶️ Method 1: Direct Execution
```
./1.sh
```

✅ Conditions:

* You must be in the same directory

* Script must have execute permission
___

### ▶️ Method 2: Using Bash
```
bash 1.sh
```

✔ This method:

* Does not require execute permission

* Is commonly used for testing or checking scripts
___


## 📌 9. Output Example 📤
```
Hello World
```

# Control Structures in Shell Script

## Types

  **1. Conditional Statements (if, if-else, elif)**

  **2. Loops (for, while, until)**

## Conditional Statements

### Description

- Conditional statements are used for decision making.

### if-else Syntax
```
if [ condition ]
then
    commands
else
    commands
fi
```
## 1.File & Directory Test Conditions

| Operator | Description                       |
| -------- | --------------------------------- |
| `-f`     | File exists and is a regular file |
| `-d`     | Directory exists                  |
| `-r`     | File has read permission          |
| `-w`     | File has write permission         |
| `-x`     | File has execute permission       |
| `-s`     | File exists and is not empty      |

## 2.String Comparison Operators

| Operator | Description           |
| -------- | --------------------- |
| `=`      | Strings are equal     |
| `!=`     | Strings are not equal |
| `-z`     | String is empty       |
| `-n`     | String is not empty   |

## 3.Numerical Comparison Operators

| Operator | Description              |
| -------- | ------------------------ |
| `-eq`    | Equal to                 |
| `-ne`    | Not equal to             |
| `-gt`    | Greater than             |
| `-ge`    | Greater than or equal to |
| `-lt`    | Less than                |
| `-le`    | Less than or equal to    |

## Loops in Shell Script
**What is a Loop?**

- A loop is used to repeat a task multiple times without writing the same code again.

## Types of Loops

### 1. for loop

### 2. while loop

### 3. until loop

## 1. for Loop

**Description**

- A for loop runs a block of code for each value in a list or range.

Syntax
```
for variable in list
 do
   commands
 done
```
