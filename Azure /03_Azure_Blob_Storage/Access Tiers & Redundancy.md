# Azure Blob Storage – Access Tiers & Redundancy

---

## 📌 Azure Blob Storage – 

---

## Access Tiers

Azure provides different access tiers based on how frequently data is accessed.

### 🔥 Hot Tier
- Best for **frequently accessed data**
- **Fastest access**
- Storage cost is **higher**
- Read and write operations are **cheaper**

---

### ❄️ Cool Tier
- Best for **infrequently accessed data**
- Used for **monthly logs** and similar data
- Storage cost is **cheaper**
- Access (read/write) cost is **more expensive** than Hot tier

---

### 🧊 Cold Tier
- Best for **rarely accessed data**
- Used for **backup files** and **legal documents**
- Storage cost is **lower than Hot and Cool**
- Access cost is **higher**
- Minimum retention period: **90 days**

---

### 🗄️ Archive Tier
- Best for **long-term**, rarely accessed data
- Used for **historical data**
- **Most cost-effective** storage option
- Data access takes **hours**

---

## 📌 Azure Storage Redundancy

Redundancy means **how many copies of data Azure keeps and where they are stored**.

---

### 1️⃣ LRS (Locally Redundant Storage)
- **3 copies** of data
- Stored in **one data center**
- If the data center fails, **data loss can occur**

---

### 2️⃣ ZRS (Zone Redundant Storage)
- **3 copies** of data
- Stored across **different availability zones**
- All copies are in the **same region**

---

### 3️⃣ GRS (Geo-Redundant Storage)
- **Total 6 copies**
- 3 copies in the **primary region**
- 3 copies in the **nearest secondary region**
- Secondary region data **cannot be accessed** unless failover happens

---

### 4️⃣ GZRS (Geo-Zone Redundant Storage)
- Combination of **ZRS + GRS**
- **6 total copies**
- 3 copies stored across **different zones** in the primary region
- 3 copies stored in the **secondary region**

---
