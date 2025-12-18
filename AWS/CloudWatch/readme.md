# 📊 Amazon CloudWatch

Amazon CloudWatch is a monitoring and observability service that helps you monitor AWS resources, applications, and services.
It collects metrics, logs, and events, allows you to set alarms, and helps you take automated actions in real time.

### 👉 In simple words:

**CloudWatch** helps you see what is happening in your AWS environment and react when something goes wrong.


## ☁️ 1. What is CloudWatch?

#### Amazon CloudWatch monitors:

* AWS resources (EC2, RDS, Lambda, ELB, S3, etc.)

* Applications running on AWS or on-premises

#### CloudWatch helps you to:

* 📊 Collect and track metrics

* 📂 Monitor and store logs

* 🚨 Create alarms

* ⚙️ Automate actions

* 📈 Visualize data using dashboards

🧠 Simple Analogy:
CloudWatch is like a health monitor for your AWS resources.


## 🧩 2. Core Components of CloudWatch

| 🔹 Component             | 📘 Description                                       |
| ------------------------ | ---------------------------------------------------- |
| **Metrics**              | Numerical performance data (example: CPUUtilization) |
| **Alarms**               | Watch metrics and trigger actions                    |
| **Logs**                 | Store and analyze system/application logs            |
| **Events (EventBridge)** | Respond to AWS resource changes                      |
| **Dashboards**           | Visual display of metrics                            |
| **Logs Insights**        | Query and analyze logs                               |


## ⚙️ 3. Common Use Cases

✔ Monitor EC2 CPU, disk, and network

✔ Track Lambda invocations and errors

✔ Store application logs centrally

✔ Send alerts using SNS

✔ Trigger Auto Scaling

✔ Create real-time dashboards


## 🏗️ 4. How CloudWatch Works (Flow)

Flow Explanation (Easy):

1️⃣ AWS services generate metrics & logs

2️⃣ CloudWatch collects them

3️⃣ You create alarms on metrics

4️⃣ Alarm triggers action (SNS / Auto Scaling / EC2 action)

5️⃣ Data is visualized on dashboards

**🟢 STEP 1: Launch EC2**

✔ Launch Amazon Linux 
✔ Connect instance

**🟢 STEP 2: Install Stress Tool**

🔧 Update system
```
sudo yum update -y
```

🔧 Install stress
```
sudo yum install stress -y
```

**🟢 STEP 3: Run Stress Command**

🔥 Increase CPU
```
stress --cpu 1
```

⏹ Stop stress
```
Ctrl + C
```

⏱ Run for fixed time
```
stress --cpu 1 --timeout 300
```

**🟢 STEP 4: Create CloudWatch Alarm**

📊 Go to CloudWatch → Alarms → Create alarm

✔ Select metric:
➡ **EC2 → Per-Instance Metrics → CPUUtilization**

✔ Condition:
➡ Threshold > 70%
➡ Time 1 minute

**🟢 STEP 5: Create NEW SNS from CloudWatch**

🔔 Alarm state: In alarm

✉ Notification:
➡ Create new SNS topic
➡ Topic name: HighCPUAlert
➡ Email endpoint: your-email@gmail.com

📨 Confirm email from inbox ✅

**🟢 STEP 6: Finish Alarm**

✔ Alarm name: EC2-High-CPU
✔ **Create alarm**
