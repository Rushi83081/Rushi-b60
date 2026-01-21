## 1. No Infrastructure Redundancy Required

In this setup, no infrastructure redundancy is required.

- Setup is simple.
- Azure places your VM anywhere in the data center.
- There is no special protection if that part of Azure fails.
- Suitable for:
  - Testing
  - Learning

---

## 2. Availability Zone

Availability Zone places VMs in **different physical zones**.

- Each zone is independent.
- You can place VMs in different zones.
- Provides better protection from failures.
- Used for high availability applications.

---

## 3. Availability Set

Availability Set ensures your VMs are placed on **different racks** in the same data center.

- If one rack fails, the other VM continues running.
- Good for 2 or more VMs running the same application.
- Protects from hardware failure.
- Does NOT protect from full zone failure.

---

# 4. VM Scale Set (Auto Scaling)

VM Scale Set is used for automatic scaling of Virtual Machines.

- Automatically increases or decreases VM count.
- Scaling is based on traffic or load.
- Used for high-traffic applications.
- Works like **Auto Scaling in AWS**.
- Commonly used for large websites.
