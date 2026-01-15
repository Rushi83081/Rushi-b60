# 🐚 Shell Scripting

---

## 📌 1. Terminal vs Shell (📍)

### 🖥️ Terminal

* A Terminal is a text-based interface.
* It is used to type and run commands.

**Examples:**

* GNOME Terminal
* iTerm
* Windows Terminal

---

### 🧠 Shell

* A Shell is a command interpreter.
* It reads commands from the terminal and executes them.
* Acts as a bridge between User and OS Kernel.

---

## 📌 2. Types of Shell 🐧 (📍)

Common shells available in Linux/Unix:

🔹 sh – Bourne Shell

🔹 bash – Bourne Again Shell (Most Popular)

🔹 zsh – Z Shell

🔹 ksh – Korn Shell

🔹 csh – C Shell

---

## 📌 3. /etc/shells 📂

* /etc/shells is a system file.
* It contains a list of valid login shells.
* The OS checks this file to know which shells are allowed.

---

## 📌 4. Shell Scripting ✍️ (📍)

* Shell scripting means writing commands in a file.
* These scripts are executed by a shell.

**Used for automation tasks like:**
📁 File handling
💾 Backups
⚙️ System administration
📊 Monitoring

---

## 📌 5. Shebang Line (#!) ⭐

### ❓ What is Shebang?

* The first line of a shell script.
* Starts with #!
* Specifies which shell should execute the script.

### 🧾 Examples

```bash
#!/bin/bash
#!/bin/sh
```

### 🔍 Why Shebang is Used?

* Instructs the OS to use a specific command interpreter.
* Decides which shell will execute the script.

### 📝 Important Points

* `#` → Sharp
* `!` → Bang
* `#!` → Shebang
* Name comes from musical notation

---

## 📌 6. Create Your First Shell Script 🚀

### ✏️ Step 1: Create a Script File (In LabEx)

```bash
vim 1.sh
```

🔔 Note: The .sh extension is not mandatory, but it is recommended for clarity.

### ✏️ Step 2: Write the Script

```bash
#!/bin/bash

echo "Hello World"
```

* `#!/bin/bash` → Shebang line (defines interpreter)
* `echo` → Used to print output on the terminal

---

## 📌 7. Give Execute Permission 🔐

Before running the script directly, give execute permission:

```bash
chmod u+x 1.sh
```

OR

```bash
chmod 700 1.sh
```

* `chmod` → Change mode (permission)
* `u+x` → Adds execute permission to the user

---

## 📌 8. Run the Script ▶️

### ▶️ Method 1: Direct Execution

```bash
./1.sh
```

**✅ Conditions:**

* You must be in the same directory
* Script must have execute permission

### ▶️ Method 2: Using Bash

```bash
bash 1.sh
```

✔ This method:

* Does not require execute permission
* Is commonly used for testing or checking scripts

---

## 📌 9. Output Example 📤

```text
Hello World
```

---

# ⚙️ Control Structures in Shell Script

## 📌 Types

1. Conditional Statements (if, if-else, elif)
2. Loops (for, while, until)

---

## 🔁 Conditional Statements

### Description

* Conditional statements are used for decision making.

### if-else Syntax

```bash
if [ condition ]
then
    commands
else
    commands
fi
```

---

### 1️⃣ File & Directory Test Conditions

| Operator | Description                       |
| -------- | --------------------------------- |
| -f       | File exists and is a regular file |
| -d       | Directory exists                  |
| -r       | File has read permission          |
| -w       | File has write permission         |
| -x       | File has execute permission       |
| -s       | File exists and is not empty      |

---

### 2️⃣ String Comparison Operators

| Operator | Description           |
| -------- | --------------------- |
| =        | Strings are equal     |
| !=       | Strings are not equal |
| -z       | String is empty       |
| -n       | String is not empty   |

---

### 3️⃣ Numerical Comparison Operators

| Operator | Description              |
| -------- | ------------------------ |
| -eq      | Equal to                 |
| -ne      | Not equal to             |
| -gt      | Greater than             |
| -ge      | Greater than or equal to |
| -lt      | Less than                |
| -le      | Less than or equal to    |

---

# 🔄 Loops in Shell Script

## ❓ What is a Loop?

* A loop is used to repeat a task multiple times without writing the same code again.

## 📌 Types of Loops

* for loop
* while loop
* until loop

---

## 🔁 1. for Loop

### Description

* A for loop runs a block of code for each value in a list or range.

### Syntax

```bash
for variable in list
 do
   commands
 done
```

---

## 🔁 2. while Loop

### Description

* A while loop executes code as long as the condition remains true.

### Syntax

```bash
while [ condition ]
 do
   commands
 done
```

---

## 🔁 3. until Loop

### Description

* An until loop runs until the condition becomes true (opposite of while loop).

### Syntax

```bash
until [ condition ]
 do
   commands
 done
```

---

# 🧩 Functions in Shell Script

## ❓ What is a Function?

* A function is a block of code written once and used multiple times.
* It performs a specific task and runs only when it is called.
* Functions make scripts clean, organized, and easy to debug.
* We can pass arguments to functions.

---

## 📌 Function Syntax

### Method 1

```bash
myfunction() {
    # code
}
```

### Method 2

```bash
function function_name {
    # code
}
```

---

## ➗ Arithmetic Operations in Shell

* `$(( ))` is used to perform arithmetic operations in shell scripting.
* Shell functions do not return values like Python or Java.
* Use echo to print output or return to send exit codes only.

### 🚦 Exit Codes

* Range: 0–255
* 0 → Success
* Non-zero → Failure

---

# 🐞 Debugging in Shell Script

## ❓ What is Debugging?

* Debugging means identifying and fixing errors in a shell script.

## ❓ Why Debugging is Needed?

* To find where the script fails
* To check script execution flow
* To know values stored in variables

---

## 📌 1. set -x (Debug Mode)

```bash
set -x
```

* Prints each command before execution
* Helps understand script flow and variable values
* Usually added at the beginning of the script

---

## 📌 2. set -e (Exit on Error)

```bash
set -e
```

* Script immediately exits if any command fails
* Prevents script from running in an error state

---

## 📌 11. Using set -xe

```bash
set -xe
```

* `-x` → Shows command execution flow
* `-e` → Stops script on error

---
# 🐚 Case and Select Statements

---

## ⭐ Case and Select Statements

---

## 📌 1) Case Statement

* Case is also control structure just like switch statement in other languages.
* Case is used when you want to match one value against many option.

---

### 🧾 Syntax

```bash
case <variable> in
pattern1)
    command
    ;;
pattern2)
    command
    ;;
*)
    default command
    ;;
esac
```

---

### 📖 Meaning of Keywords

* `<variable>` = value you are testing
* `pattern1 , pattern2` = matching pattern
* `;;` = end of case
* `*` = default case
* `esac` = is case spelled backward, it ends the case

---

## 📌 2) Select Statement

* Used to create menus automatically.
* User selects an option by number.

---

### 🧾 Syntax

```bash
select variable in option1 option2 option3
do
    commands
done
```

---

### 📝 Important Points

* To break the loop use exit or break statement.
* `#?` is the default prompt of the select statement.
* You can remove or change it using `PS3`.
* `PS3` is a variable used by the select statement.
* It shows what message is shown when a select menu asks for input.
* `PS3` stands for Prompt String.

---
