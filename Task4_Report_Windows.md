# Task 4: Setup and Use a Firewall on Windows

**Author:** ROBITH ABRAHAM  
**Date:** 2025-09-26  
**Tools:** Windows Firewall  
**Objective:** Configure and test basic firewall rules to allow or block traffic.  

---

## 1. Introduction

A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. This task focuses on configuring a firewall to block unwanted traffic (e.g., Telnet on port 23) and allow necessary traffic.  

**Outcome:** Basic firewall management skills and understanding of network traffic filtering.

---

## 2. Windows Firewall Configuration

### Step 1: Open Windows Firewall
- Press `Win + R`, type `firewall.cpl`, and press Enter.
- The Windows Defender Firewall window appears.

### Step 2: View Current Firewall Rules
- Navigate to **Advanced Settings** → **Inbound Rules**.
- Current rules are listed for all applications and ports.

### Step 3: Block Inbound Telnet Traffic (Port 23)
1. Click **New Rule…** on the right panel.
2. Select **Port** → Next.
3. Choose **TCP**, specify port `23` → Next.
4. Select **Block the connection** → Next.
5. Apply to all profiles → Next.
6. Name the rule: `Block Telnet Port 23` → Finish.

**Screenshot Placeholder:**  
![Windows Firewall Block Telnet](https://via.placeholder.com/600x200.png?text=Windows+Firewall+Block+Telnet+Port+23)

### Step 4: Test the Rule
- Attempt to connect to the local machine via Telnet (`telnet <IP> 23`)  
- Result: Connection blocked successfully.

### Step 5: Remove the Test Block Rule
- Select `Block Telnet Port 23` → Right-click → Delete.  
- Firewall restored to original state.

---

## 3. Summary

- Windows Firewall filters traffic based on rules specifying **ports, protocols, and IP addresses**.  
- Blocking Telnet (port 23) prevents insecure remote access.  
- Regular monitoring and rule management are crucial for network security.

---

**References / Notes:**  
- Windows Firewall: [Microsoft Documentation](https://support.microsoft.com/en-us/windows/windows-firewall-settings)
