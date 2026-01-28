# 📊 Amazon CloudWatch

Amazon CloudWatch is a monitoring and observability service that helps you monitor AWS resources, applications, and services in real time.  
It collects **metrics, logs, and events**, allows you to create **alarms**, and enables **automated actions** when something goes wrong.

---

## 👉 In Simple Words

**Amazon CloudWatch** helps you understand **what is happening** in your AWS environment and **react immediately** when issues occur.

---

## ☁️ 1. What is Amazon CloudWatch?

Amazon CloudWatch monitors:

- AWS resources (EC2, RDS, Lambda, ELB, S3, etc.)
- Applications running on AWS or on-premises

### ⭐ CloudWatch Helps You To:
- 📊 Collect and track metrics  
- 📂 Monitor and store logs  
- 🚨 Create alarms  
- ⚙️ Automate actions  
- 📈 Visualize data using dashboards  

🧠 **Simple Analogy:**  
CloudWatch is like a **health monitor** for your AWS infrastructure.

---

## 🧩 2. Core Components of CloudWatch

| Component | Description |
|---------|-------------|
| **Metrics** | Numerical performance data (e.g., CPUUtilization) |
| **Alarms** | Monitor metrics and trigger actions |
| **Logs** | Store and analyze system/application logs |
| **Events (EventBridge)** | Respond to AWS resource changes |
| **Dashboards** | Visual representation of metrics |
| **Logs Insights** | Query and analyze logs |

---

## ⚙️ 3. Common Use Cases

- Monitor EC2 CPU, disk, and network usage  
- Track Lambda invocations and errors  
- Centralized log storage  
- Send alerts using SNS  
- Trigger Auto Scaling actions  
- Build real-time monitoring dashboards  

---

## 🏗️ 4. How CloudWatch Works (Flow)

### 🔁 Flow Explanation

1. AWS services generate metrics and logs  
2. CloudWatch collects the data  
3. Alarms are created on metrics  
4. Alarm triggers an action (SNS / Auto Scaling / EC2 action)  
5. Metrics are visualized using dashboards  

---

## ▶️ Practical: Monitor EC2 CPU Usage Using CloudWatch

### 🟢 Step 1: Launch EC2 Instance

- Launch an **Amazon Linux** EC2 instance
- Connect to the instance using SSH

---

### 🟢 Step 2: Install Stress Tool

Update the system:
```bash
sudo yum update -y
```

---

## 🟢 Step 3: Generate CPU Load

- Install the **stress** tool:
```bash
sudo yum install stress -y
```

- Increase CPU usage:
```bash
stress --cpu 1
```

- Stop the stress command:
```bash
Ctrl + C
```

- Run CPU stress for a fixed duration:
```bash
stress --cpu 1 --timeout 300
```

## 🟢 Step 4: Create CloudWatch Alarm

1. Go to **CloudWatch → Alarms → Create alarm**
2. Select metric:
   - **EC2 → Per-Instance Metrics → CPUUtilization**
3. Configure the condition:
   - **Threshold:** Greater than 70%
   - **Period:** 1 minute

---

## 🟢 Step 5: Create SNS Notification

- **Alarm state:** In alarm
- Create a new SNS topic:
  - **Topic name:** `HighCPUAlert`
  - **Protocol:** Email
  - **Endpoint:** `your-email@gmail.com`
- Confirm the subscription from your email inbox ✅

---

## 🟢 Step 6: Finish Alarm Creation

- **Alarm name:** `EC2-High-CPU`
- Click **Create alarm**

---

## ✅ Final Result

- EC2 CPU utilization crosses 70%
- CloudWatch alarm is triggered
- SNS sends an email notification
- CPU metrics are visible in CloudWatch dashboards

---

## 🎯 Summary

Amazon CloudWatch enables you to:
- Monitor AWS resources effectively
- Detect performance issues early
- Automate alerting and responses
- Maintain high availability and reliability
