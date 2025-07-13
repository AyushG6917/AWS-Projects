# ☁️ Cloud Gatekeeper – SSH Access in a Tiered VPC 🔐

> _“When you can’t go through the front door, take the secure path through the gatekeeper!”_

Welcome to **Cloud Gatekeeper** – a project that puts your networking, security, and SSH skills to the test. This setup demonstrates how to securely access private EC2 instances using a public "gatekeeper" instance inside a well-structured AWS VPC.

---

## 🧠 Project Goal

Create a secure, tiered VPC architecture where:
- Public EC2s can access the internet.
- Private EC2s are completely isolated.
- SSH access to private EC2s is **only possible** by hopping through public EC2s – like a true **jump host** setup.

---

## 🎯 Objectives

✅ Create a **VPC** with:
- 2️⃣ Public Subnets (AZ 1)  
- 2️⃣ Private Subnets (AZ 2)

✅ Launch **4 EC2 Instances**:
- One in each subnet  
- Only Public EC2s have internet access

✅ Implement **SSH hopping**:
- SSH → Public EC2 #1 → Private EC2 #1 → Private EC2 #2  
- **No direct internet access** for private instances

---

## 🛠️ Tools & AWS Services Used

- **Amazon VPC**
- **Subnets (Public & Private)**
- **Route Tables**
- **Internet Gateway**
- **EC2 Instances (Ubuntu)**
- **SSH Key Management**
- **Security Groups**

---

## 🧭 Architecture Diagram

v
               ┌────────────────────────────┐
               │      VPC: 10.0.0.0/18      │
               │                            │
               │   ┌────────────┐           │
               │   │Public_Sub1 │────────┐  │
               │   └────────────┘        │  │
               │   ┌────────────┐        ▼  │
               │   │Public_Sub2 │     Public_EC2s
               │   └────────────┘        ▲  │
               │   ┌────────────┐        │  │
               │   │Private_Sub1│────────┘  │
               │   └────────────┘     Private_EC2s
               │   ┌────────────┐           │
               │   │Private_Sub2│───────────┘
               └────────────────────────────┘
                      🔐 SSH Jump Only


---

## 🚀 Steps to Reproduce

1. **Create VPC**  
   - CIDR: `10.0.0.0/18`  
   - Enable DNS hostnames

2. **Create Subnets**  
   - Public_Subnet_1: `10.0.0.0/20`  
   - Public_Subnet_2: `10.0.0.16/20`  
   - Private_Subnet_1: `10.0.0.32/20`  
   - Private_Subnet_2: `10.0.0.48/20`

3. **Route Tables**  
   - Attach **Internet Gateway** only to public route table  
   - Private route table stays isolated

4. **Launch EC2 Instances**  
   - Ubuntu AMI, same key pair  
   - Only Public_EC2_1 has public IP

5. **SSH Access Flow**
   - SSH into Public_EC2_1 from your PC  
   - From there, SSH into other instances using their **private IPs**

6. **Permission Fix** (if needed)  
   ```bash
   chmod 400 key.pem

---

## 🔍 Key Concepts

- VPC & Subnetting (CIDR blocks)
- Internet Gateway + Route Table association
- SSH tunneling / Jump host model
- Public vs Private IP addressing
- EC2 Key Pair reuse across instances
- Tiered cloud architecture with controlled access

---

## 💡 Why This Project?

This project demonstrates a **real-world use case** of secure networking architecture in AWS.  
It showcases how to:
- Safely access private resources using bastion hosts
- Build tiered VPC structures with isolated zones
- Control access without exposing the backend to the internet

Perfect for those learning AWS, DevOps, or preparing for cloud certification projects.

---

## 🏁 What’s Next?

- ⛏️ Automate the entire setup using **Terraform** or **AWS CloudFormation**
- 📊 Add **CloudWatch Monitoring** for EC2 instances
- 🧑‍💼 Implement **IAM Roles and Policies** for finer-grained access control
- 🔒 Explore **AWS SSM Session Manager** as an alternative to SSH
- 🧪 Build a frontend dashboard (MERN) to visualize VPC and instance status

---

## 👨‍💻 Author

**Ayush**  
_Mechanical Engineering Grad | AWS | DevOps | Full-Stack Learner_  
Currently learning the **MERN stack** and building projects that combine **cloud** and **full-stack** skills.

📫 [LinkedIn](https://linkedin.com/in/ayush-gowarkar)  
🌐 Portfolio: Coming Soon!

---


