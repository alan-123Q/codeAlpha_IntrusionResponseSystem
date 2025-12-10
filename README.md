# codeAlpha_IntrusionResponseSystem
A network-based Intrusion Detection System (IDS) built to monitor and analyze network traffic for suspicious or malicious activities. Includes rule configuration, alert generation, and traffic monitoring using open-source security tools.

---

# 🛡️ Network-Based Intrusion Detection System (NIDS)

![Status](https://img.shields.io/badge/Project-Completed-brightgreen)
![Snort](https://img.shields.io/badge/Snort-IDS-red)
![Linux](https://img.shields.io/badge/Linux-Ubuntu%20%7C%20Kali-blue)
![CodeAlpha](https://img.shields.io/badge/Internship-CodeAlpha-orange)

A **Network-Based Intrusion Detection System (NIDS)** built using **Snort** to detect malicious activities, suspicious packets, and network-based attacks.
This project is part of the **CodeAlpha Cybersecurity Internship** and demonstrates practical defensive security skills.

---

# 📌 Table of Contents

* [Requirements](#-requirements)
* [Initial Setup](#-initial-setup)
* [Snort Installation](#-snort-installation)
* [Configuration](#-configuration)
* [Running Snort](#-running-snort)
* [Logging Alerts](#-logging-alerts)
* [Example Alerts](#-example-alerts)
* [Screenshots](#-screenshots)
* [Conclusion](#-conclusion)

---

# 🛠 Requirements

| Component           | Purpose                    |
| ------------------- | -------------------------- |
| **VirtualBox**      | Virtualization environment |
| **Kali Linux**      | Attack machine             |
| **Ubuntu Server**   | IDS machine (Snort)        |
| **Snort**           | Network-Based IDS          |
| **Nmap**            | Port scanning & testing    |
| **Active Internet** | Package installation       |

---

# 📥 Initial Setup

### **1️⃣ Install VirtualBox**

### **2️⃣ Import Kali Linux VM**

### **3️⃣ Download Ubuntu Server ISO**

🔗 [https://ubuntu.com/download/server](https://ubuntu.com/download/server)

### **4️⃣ Create Ubuntu VM and attach ISO**

---

### ⚠️ Network Configuration (Important)

Configure **both Kali and Ubuntu Server**:

| Setting          | Value               |
| ---------------- | ------------------- |
| Adapter          | **Bridged Adapter** |
| Promiscuous Mode | **Allow All**       |

Enables packet capture and attack simulation.

---

# 🐍 Snort Installation (Ubuntu)

### **1️⃣ Check IP Address**

```bash
ifconfig
```

### **2️⃣ Update Packages**

```bash
sudo apt update && sudo apt upgrade -y
```

### **3️⃣ Install Snort**

```bash
sudo apt install snort
```

Enter your network range when prompted, e.g.:

```
192.168.xx.0/24
```

### **4️⃣ Verify Installation**

```bash
snort -V
```

---

# ⚙️ Configuration

### **1️⃣ Modify Local Rules (Optional)**

```bash
sudo nano /etc/snort/rules/local.rules
```

### **2️⃣ Open Main Config File**

```bash
sudo nano /etc/snort/snort.conf
```

---

# ▶️ Running Snort

### **1️⃣ Test Configuration**

```bash
sudo snort -T -c /etc/snort/snort.conf -i enp0s3
```

### **2️⃣ Run IDS in Alert Mode**

```bash
sudo snort -A console -c /etc/snort/snort.conf -i enp0s3
```

### **3️⃣ From Kali — Generate Traffic**

#### Nmap Scan:

```bash
nmap -Pn 192.168.x.x
```

#### Send Ping Request:

```bash
ping 192.168.x.x
```

Snort will display alerts in real-time.

---

# 📝 Logging Alerts

### **1️⃣ Run Snort with Logging**

```bash
sudo snort -A console -c /etc/snort/snort.conf -i enp0s3 -l /var/log/snort
```

### **2️⃣ View Alert Logs**

```bash
sudo cat /var/log/snort/snort.alert.fast
```

---

# 📊 Example Alerts

| Alert Type                 | Description                |
| -------------------------- | -------------------------- |
| **ICMP Ping Detected**     | Ping scan from attacker    |
| **TCP SYN Scan**           | Port scan via Nmap         |
| **UPnP Discovery Attempt** | Suspicious network probing |

---

# 🖼 Screenshots

*( `/screenshots` folder.)*

* IP Address
* Snort Version
* Snort Rules
* Alerts in Terminal
* Nmap Scan Output
* Ping Output

---

# ✅ Conclusion

This project successfully demonstrates a working **Network-Based Intrusion Detection System** using Snort.
It showcases:

✔ Packet capturing
✔ Attack detection (Nmap, ICMP, TCP scans)
✔ Real-time alerts
✔ Log file generation
✔ Hands-on cybersecurity skills

---

