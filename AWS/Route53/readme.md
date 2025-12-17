# 🌐 AWS 'Route 53' 

---

## 1️⃣ What is Route 53? 

* **Route 53** is an **AWS DNS (Domain Name System) service**.
* It is used to **route user traffic to AWS resources**.

### 🔹 Types of Route 53

1. **Public Route 53** – Used for **internet‑facing domains**
2. **Private Route 53** – Used **inside VPC (internal routing)**

🧠 **Viva Line:**

> Route 53 is a DNS service used to route traffic using public and private hosted zones.

---

## 2️⃣ Record Types (Only Main Types)

| Record Type      | Purpose                               |
| ---------------- | ------------------------------------- |
| **A Record**     | Maps domain name to **IPv4 address**  |
| **AAAA Record**  | Maps domain name to **IPv6 address**  |
| **CNAME Record** | Maps one domain to **another domain** |
| **NS Record**    | Defines **name servers**              |
| **MX Record**    | Used for **mail servers**             |

🧠 **Viva Line:**

> A, AAAA, CNAME, NS, and MX are the main DNS record types.

---

## ⭐ Alias Record (Very Important for Viva)

### 🔹 What is Alias Record?

* **Alias record** is an **AWS‑specific DNS record** in Route 53.
* It works like **CNAME**, but **better**.
* Used to map domain name to **AWS resources**.

🧠 Viva Line:

> Alias record maps domain name to AWS resources without using CNAME.

---

### 🔹 Why Alias is Used?

* **CNAME cannot be used at root domain** (`example.com`)
* **Alias CAN be used at root domain**
* Alias is **free of cost**
* Alias supports **health checks**

---

### 🔹 AWS Resources Supported by Alias

* **ELB (Load Balancer)**
* **CloudFront**
* **S3 Static Website**
* **API Gateway**

---

### 🔹 Alias vs CNAME (Viva Favorite)

| Alias                | CNAME                 |
| -------------------- | --------------------- |
| AWS‑specific         | Standard DNS          |
| Works at root domain | ❌ Not allowed at root |
| Free                 | Charged               |
| Faster & reliable    | Normal                |

🧠 **One‑Line Viva Answer:**

> Alias is preferred over CNAME in Route 53 because it works at root domain and supports AWS services.

---

## 3️⃣ Routing Policy

* Routing policy decides **how traffic is routed** to resources.

### 🔹 Types of Routing Policies

1. **Simple Routing** – Single resource
2. **Weighted Routing** – Traffic distributed by weight
3. **Latency Routing** – Routes to lowest latency region
4. **Failover Routing** – Primary and secondary routing
5. **Geolocation Routing** – Based on user location
6. **Multi‑Value Answer Routing** – Multiple healthy resources

🧠 **Viva Line:**

> Routing policy controls how Route 53 responds to DNS queries.

---

## 4️⃣ Practical Steps: Map EC2 IP to Domain Name 

### 🔹 Step 1: Launch EC2 Instance

* Go to **AWS Console → EC2**
* Launch an **EC2 instance**
* Note down the **Public IPv4 Address** of EC2

🧠 Viva Line:

> EC2 public IP is required to map domain name.

---

### 🔹 Step 2: Buy Domain from Hostinger

* Go to **Hostinger**
* Purchase a domain (example: `mywebsite.com`)
* Go to **DNS / Name Server settings**

🧠 Viva Line:

> Domain can be purchased from third-party providers like Hostinger.

---

### 🔹 Step 3: Create Hosted Zone in Route 53

* Go to **Route 53 → Hosted Zones**
* Click **Create Hosted Zone**
* Enter domain name: `mywebsite.com`
* Choose **Public Hosted Zone**
* Create hosted zone

🧠 Viva Line:

> Hosted zone stores DNS records for the domain.

---

### 🔹 Step 4: Copy Name Servers from Route 53

* After creating hosted zone, Route 53 provides **NS records**
* Copy all **Name Server (NS)** values

Example:

```
ns-123.awsdns-45.com
ns-456.awsdns-78.net
```

---

### 🔹 Step 5: Update Name Servers in Hostinger

* Go to **Hostinger → DNS / Nameserver section**
* Replace default name servers
* Paste **Route 53 name servers**
* Save changes

🧠 Viva Line:

> Domain is connected to Route 53 using name servers.

---

### 🔹 Step 6: Create A Record (Map IP to Domain)

* Go to **Route 53 → Hosted Zone**
* Click **Create Record**
* Record Type: **A**
* Record Name: (leave empty for root domain)
* Value: **EC2 Public IP**
* Routing Policy: **Simple**
* Save record

🧠 Viva Line:

> A record maps domain name to EC2 public IP.

---

### 🔹 Step 7: Access Website Using Domain Name

* Open browser
* Enter:

```
http://mywebsite.com
```

* Domain now points to EC2 instance

⏳ DNS propagation may take **few minutes to hours**

---

## 🧠 One-Line Full Process (Viva)

> Launch EC2, buy domain from Hostinger, create hosted zone in Route 53, update name servers, and map EC2 IP using A record.

---

## ✅ Quick Viva Summary

> Route 53 maps domain names to IP addresses using hosted zones and DNS records.
