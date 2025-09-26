# Cybersec-internship--firewall-report-task4
# Task 4: Firewall Setup and Use on Windows

## 1. Objective
[cite_start]The objective of this task was to configure and test basic firewall rules on Windows to allow or block specific network traffic, demonstrating a fundamental understanding of network traffic filtering. [cite: 4, 15]

## 2. Tools Used
* **Operating System:** Windows 11
* [cite_start]**Firewall Software:** Windows Defender Firewall with Advanced Security [cite: 5]
* **Testing Tool:** Telnet Client

## 3. Steps Taken to Configure and Test the Firewall

[cite_start]I used the Windows Defender Firewall graphical user interface (GUI) to perform the following actions[cite: 13]:

1.  **Opened Advanced Settings:** I navigated to `Windows Defender Firewall` and opened `Advanced settings` to access the rule configuration panel.

2.  **Listed Current Rules:** I selected "Inbound Rules" to view the existing firewall configuration.
    * *Screenshot showing the list of active inbound rules:*
    * ![Windows Inbound Rules](screenshots/1_inbound_rules_list.png)

3.  [cite_start]**Added a Rule to Block Port 23 (Telnet):** I created a new inbound rule to block TCP traffic on port 23, which is used for Telnet. [cite: 9]
    * **Rule Type:** Port
    * **Protocol and Ports:** TCP, Specific local port: 23
    * **Action:** Block the connection
    * **Profile:** All (Domain, Private, Public)
    * **Name:** `Block Telnet (Task 4)`

4.  **Tested the Block Rule:** I opened the Windows Command Prompt and used the Telnet client to attempt a connection to port 23 on my local machine. [cite_start]As expected, the connection failed, proving the firewall rule was working correctly. [cite: 10]
    * *Screenshot showing the failed Telnet connection attempt:*
    * ![Failed Telnet Test](screenshots/2_telnet_test_failed.png)

5.  [cite_start]**Removed the Test Rule:** To restore the system to its original state, I located the `Block Telnet (Task 4)` rule in the list, right-clicked, and deleted it. [cite: 12]

## 4. Summary of How a Firewall Filters Traffic
A firewall acts as a security guard for a network. [cite_start]It inspects all data packets trying to enter or leave the network and decides whether to allow them or block them based on a set of security rules. [cite: 14] [cite_start]For example, the rule I created told the firewall to inspect all incoming packets and if any packet was destined for TCP port 23, it should be dropped, effectively blocking Telnet traffic. [cite: 9]

## 5. Interview Questions & Answers

**1. [cite_start]What is a firewall?** [cite: 17]
A firewall is a network security system, either hardware or software-based, that controls incoming and outgoing network traffic based on predetermined security rules. It establishes a barrier between a trusted internal network and an untrusted external network, such as the Internet.

**2. [cite_start]Difference between stateful and stateless firewall?** [cite: 18]
* **Stateless Firewall:** Inspects each packet in isolation. It has no memory of past packets and makes decisions based solely on the source/destination IP addresses and ports. It's fast but less secure.
* **Stateful Firewall:** Keeps track of the state of network connections (e.g., TCP streams). It makes decisions based on the context of the traffic, not just individual packets. This allows it to understand if an incoming packet is part of an established, legitimate conversation, making it much more secure.

**3. [cite_start]What are inbound and outbound rules?** [cite: 19]
* **Inbound Rules:** Apply to traffic coming *into* your computer or network from an external source. For example, blocking an external user from accessing a web server on your machine.
* **Outbound Rules:** Apply to traffic going *out from* your computer or network. For example, preventing a piece of malware on your computer from "phoning home" to a command-and-control server.

**4. [cite_start]How does UFW simplify firewall management?** [cite: 20]
UFW (Uncomplicated Firewall) is a frontend for `iptables` in Linux. It simplifies firewall management by providing a much simpler, user-friendly command syntax. Instead of writing complex `iptables` chains, a user can run simple commands like `sudo ufw allow ssh`, making firewall configuration less error-prone and more accessible.

**5. [cite_start]Why block port 23 (Telnet)?** [cite: 21]
Port 23 is used by Telnet, which is an extremely insecure protocol. It transmits all data, including usernames and passwords, in plaintext. Anyone monitoring the network traffic can easily steal these credentials. It has been replaced by secure alternatives like SSH (Secure Shell) on port 22.

**6. [cite_start]What are common firewall mistakes?** [cite: 22]
* **"Allow Any" Rules:** Creating overly permissive rules that allow all traffic from any source, which defeats the purpose of the firewall.
* **Incorrect Rule Order:** In some firewalls, rules are processed in order. Placing a broad "allow" rule before a specific "deny" rule can render the deny rule useless.
* **Not Reviewing Logs:** Failing to monitor firewall logs, which can provide early warnings of attacks or misconfigurations.
* **Forgetting Outbound Rules:** Only focusing on inbound threats and allowing all outbound traffic, which can allow malware to communicate with external servers.

**7. [cite_start]How does a firewall improve network security?** [cite: 23]
A firewall is a primary line of defense. It improves security by:
* **Preventing Unauthorized Access:** Blocking malicious actors from accessing systems on the network.
* **Stopping Malware:** It can block known malicious domains and prevent malware from spreading or communicating.
* **Enforcing Access Policies:** It allows administrators to define exactly which services are accessible to the outside world, reducing the attack surface.

**8. [cite_start]What is NAT in firewalls?** [cite: 24]
NAT stands for Network Address Translation. In the context of a firewall, it's a feature that allows multiple devices on a private network (with private IP addresses like 192.168.x.x) to share a single public IP address to access the internet. It also acts as a security barrier by hiding the internal network structure from the outside world, as an external device can only see the firewall's public IP address.
