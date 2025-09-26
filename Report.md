# 🔒 Cyber Security Internship – Task 4: Firewall Configuration

## 📌 Objective
The goal of this task is to configure and test basic firewall rules to **block insecure services** like Telnet (Port 23) and **allow secure services** like SSH (Port 22), using **Windows Firewall** and **UFW (Linux)**.  

---

## 🛠 Tools Used
- **Windows Firewall (GUI/Advanced Settings)**  
- **UFW (Uncomplicated Firewall)** on Linux  

---

## ⚡ Procedures  

### 🔹 On Linux (UFW)
```bash
# View firewall status
sudo ufw status verbose

# Block Telnet (port 23)
sudo ufw deny 23

# Allow SSH (port 22)
sudo ufw allow 22

# Delete Telnet rule after testing
sudo ufw delete deny 23
```

### 🔹 On Windows Firewall
1. Open **Control Panel → System and Security → Windows Defender Firewall**.  
2. Select **Advanced Settings**.  
3. Go to **Inbound Rules → New Rule**.  
4. Choose **Port → TCP 23 → Block Connection**.  
5. Test the rule by connecting to port 23 (should be blocked).  
6. To remove, delete the created rule.  

---

## 📊 Outcome
- Successfully **blocked Telnet (Port 23)** to prevent insecure communication.  
- Allowed **SSH (Port 22)** for secure remote login.  
- Learned to configure firewall rules using both **command-line (Linux)** and **GUI (Windows)** methods.  
- Gained an understanding of **inbound vs outbound rules** and the importance of firewall management.  

---

## ❓ Interview Questions & Answers
- **Q: What is a firewall?**  
  A firewall is a network security system that monitors and controls traffic based on predefined rules.  

- **Q: Why block Telnet (Port 23)?**  
  Because it sends data in plain text, making it vulnerable to interception and attacks.  

- **Q: How does UFW help?**  
  It simplifies firewall rule management with easy commands on Linux.  

- **Q: What is NAT in firewalls?**  
  Network Address Translation maps private IPs to public ones, improving security and conserving IP addresses.  

---

## 📂 Files in Repository
- `README.md` → General project overview  
- `Task4_Firewall_Report.pdf` → Full detailed report  
- `Report.md` → This markdown submission report  
- `screenshot.png` → Firewall rules placeholder screenshot  

---

✅ **This report is ready to submit in your GitHub repo.**
