# Nmap-Network-Enumeration-Lab

## Author
**Andrew**

## Project Overview
This project demonstrates the fundamentals of network enumeration and reconnaissance using **Nmap** on **Kali Linux** within a controlled virtual lab environment.

The objective of this lab was to:
- Install and verify Nmap
- Identify local network interfaces
- Discover active hosts
- Detect operating systems
- Enumerate open ports and exposed services
- Analyze potential security risks

---

# Lab Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux |
| Tool Used | Nmap 7.99 |
| Virtualization | VMware |
| Target System | Metasploitable-like Vulnerable Machine |
| Network Range | 192.168.37.0/24 |

---

# Step 1 — Nmap Installation Verification

```bash
sudo apt install nmap -y
```

The installation output confirmed that the latest version of Nmap was already installed on the Kali Linux system.

---

# Step 2 — Network Interface Identification

```bash
ip a
```

The `ip a` command was used to identify:
- Active network interfaces
- Assigned IP addresses
- Network configuration

The active interface was:
```bash
eth0
```

Assigned IP range:
```bash
192.168.37.x
```

---

# Step 3 — Host Discovery Scan

```bash
nmap -sn 192.168.37.0/24
```

This scan performed a ping sweep across the subnet to identify live hosts.

## Results
- Multiple active devices were discovered
- VMware virtual devices were detected
- The target machine `192.168.37.130` was identified as active

---

# Step 4 — Operating System Detection

```bash
nmap -O 192.168.37.130
```

This scan was used to:
- Detect the operating system
- Identify exposed services
- Enumerate open ports

## Detected Operating System
```bash
Linux Kernel 2.6.x
```

---

# Open Ports and Services

| Port | Service |
|---|---|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 111 | RPCBind |
| 139 | NetBIOS |
| 445 | Microsoft-DS |
| 3306 | MySQL |
| 5432 | PostgreSQL |
| 5900 | VNC |

---

# Security Analysis

The target machine exposed several insecure and outdated services.

## Important Findings
- Telnet service enabled
- Outdated Linux kernel
- Multiple remote access services exposed
- Database services publicly accessible
- Large attack surface identified

These findings demonstrate how enumeration helps security professionals identify potential vulnerabilities before exploitation.

---

# Skills Demonstrated

- Network Enumeration
- Host Discovery
- Port Scanning
- OS Fingerprinting
- Service Enumeration
- Basic Reconnaissance
- Cybersecurity Documentation

---

# Conclusion

This lab successfully demonstrated the use of Nmap for professional network reconnaissance and enumeration.

The project provided practical understanding of:
- Discovering devices on a network
- Detecting operating systems
- Enumerating services
- Identifying exposed attack surfaces

This exercise strengthened foundational penetration testing and cybersecurity assessment skills.

---

# Disclaimer

This project was conducted in a controlled lab environment for educational and ethical cybersecurity learning purposes only.
