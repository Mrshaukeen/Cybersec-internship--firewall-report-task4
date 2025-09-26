# Cybersec-internship--firewall-report-task4
# Task 4: Firewall Configuration

## 1. Objective
[cite_start]The objective of this task was to configure and test basic firewall rules on [Your OS: Windows/Linux] to allow and block specific network traffic. [cite: 4]

## 2. Tools Used
* **Operating System:** [e.g., Ubuntu 22.04 or Windows 11]
* [cite_start]**Firewall Software:** [e.g., UFW (Uncomplicated Firewall) or Windows Defender Firewall] 
* **Testing Tool:** [e.g., telnet]

## 3. Steps Taken

### [For Linux Users]
I followed these steps to configure UFW:
1.  **Checked UFW Status & Enabled:** `sudo ufw status`, `sudo ufw enable`
2.  **Allowed SSH Traffic:** `sudo ufw allow ssh`
3.  **Blocked Telnet (Port 23):** `sudo ufw deny 23/tcp`
    * *Screenshot of firewall status showing the new rule:*
    * ![UFW Status with Block Rule](screenshots/your_screenshot_1.png)
4.  **Tested the Block Rule:** Used `telnet localhost 23` to confirm the connection was refused.
    * *Screenshot of the failed connection:*
    * ![Telnet Test Failed](screenshots/your_screenshot_2.png)
5.  **Removed the Rule:** `sudo ufw delete deny 23/tcp`

### [For Windows Users]
I used the Windows Defender Firewall GUI to perform the following actions:
1.  **Navigated to Advanced Settings** and viewed existing inbound rules.
    * *Screenshot of inbound rules list:*
    * ![Windows Inbound Rules](screenshots/your_screenshot_1.png)
2.  **Created a New Inbound Rule** to block TCP traffic on port 23.
3.  **Tested the Rule** using the Telnet client in the command prompt, which failed as expected.
    * *Screenshot of the failed Telnet connection:*
    * ![Windows Telnet Test Failed](screenshots/your_screenshot_2.png)
4.  **Deleted the Rule** to clean up the configuration.

## 4. How a Firewall Filters Traffic
A firewall acts as a barrier between a trusted internal network and an untrusted external network (like the internet). It works by inspecting incoming and outgoing data packets and checking them against a set of predefined security rules. If a packet matches a rule that allows it, it passes through. If it matches a rule that blocks it, it is discarded. [cite_start]This prevents unauthorized access, malware, and other cyber threats from entering the network. [cite: 14]

## 5. Answers to Interview Questions
*(This is a great way to show extra effort!)*

* [cite_start]**What is a firewall?** A firewall is a network security device or software that monitors and controls network traffic based on security rules. [cite: 17]
* **Difference between stateful and stateless firewall?** A stateless firewall inspects packets individually and has no memory of past connections. [cite_start]A stateful firewall monitors the full state of active connections and makes decisions based on the context of the traffic, which is more secure. [cite: 18]
* [cite_start]...*continue answering the other questions from the PDF*... [cite: 19, 20, 21, 22, 23, 24]
