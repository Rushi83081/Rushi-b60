# 📘 AWS Lambda Practical

## 🟢 Step 1: Create IAM Role

**🔐 IAM → Roles → Create role**

✔ Service: Lambda

✔ Policy: AmazonEC2FullAccess

✔ Role name: Lambda-EC2-Role


## 🟢 Step 2: Create Lambda Function

☁️ Lambda → Create function

✔ Name: EC2-Start-Stop

✔ Runtime: Python 3.9

✔ Role: Lambda-EC2-Role


## 🟢 Step 3: Add EC2 START Code

💻 Lambda → Code tab

📌 Paste EC2 start code

✔ Click Deploy

**🧪 Test event:**
```
{ 
"action": "start"
}
```
▶️ Result: EC2 STARTS

## 🟢 Step 4: Add EC2 STOP Code

💻 Replace code with EC2 stop code

✔ Click Deploy

**🧪 Test event:**
```
{ 
"action": "stop" 
}
```
⏹ Result: EC2 STOPS

## 🟢 Step 5: Verify

🖥️ EC2 Console

✔ Instance state changes:

▶️ Running

⏹ Stopped
