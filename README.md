# Cybersecurity Portfolio - Ahmad Fany Rizqiyanto

This repository contains hands-on technical reports, security assessments, and practical documentation developed through cybersecurity labs, bootcamp projects, and self-learning activities.

## 🏆 Bootcamp Achievement

- 🥇 Best Final Project Defensive
- 🥈 1st Runner-Up Performer
- 🎯 Final Score: 93.76/100
- 🔵 Final Project Defensive: 100/100
- 🔴 Final Project Offensive: 78.33/100

## 🔴 Red Team

### 1. Injection Attacks Report

Assessment conducted within the Damn Vulnerable Web Application (DVWA) laboratory environment.

Topics covered:

* SQL Injection
* Reflected Cross-Site Scripting (XSS)
* Vulnerability Validation
* Risk Analysis

📄 [Injection Attacks Report](./Red%20Team/Injection%20Attacks%20Report.pdf)

---

### 2. Web Application Penetration Testing Assessment

Grey-Box Web Application Penetration Testing conducted against an e-commerce platform.

Activities performed:

* Reconnaissance
* Application Mapping
* Vulnerability Discovery
* Exploitation Validation
* Risk Assessment
* Security Reporting

Key Findings:

* SQL Injection
* Business Logic Vulnerability
* Credential Exposure
* Exposed Git Repository

Artifacts:

📄 [Web Application Penetration Testing Report](./Red%20Team/Web%20Application%20Penetration%20Testing%20Report%20-%20Redacted.pdf)

🖼️ [Attack Chain Diagram](./Red%20Team/Attack%20Chain%20-%20Web%20App%20Pentest.png)

---

## 🔵 Blue Team

Projects will be added during the Blue Team phase, including:

### 1. Digital Forensics & Wazuh SIEM Threat Investigation

Comprehensive digital forensics investigation and threat hunting analysis on a production-like e-commerce server (`srv974671`). The assessment correlates multiple digital artifacts—including Wazuh SIEM alerts, SSH authentication logs, MySQL query logs, Apache web logs, and application source code—to identify security incidents, misconfigurations, and web application vulnerabilities.

Activities performed:
* SIEM Alert Correlation & Log Analysis (Wazuh Rules: 5503, 5551, 5710, 5712, 5760)
* Multi-Source Evidence Mapping (SSH Auth Log, Apache Access/Error Log, MySQL Query Log)
* Incident Timeline Reconstruction & Attack Vector Identification
* Source Code Security Audit (PHP Input Validation & Upload Handler Analysis)
* Risk Rating Assessment (CVSS v3.1 Scoring)
* Incident Response & Mitigation Roadmap (Immediate to Long-Term Hardening)

Key Findings:
* **F-01 (Server Misconfiguration):** Insecure OpenSSH Configuration (`PermitRootLogin yes`, `PasswordAuthentication yes`)
* **F-02 (Application Vulnerability):** Local File Inclusion (LFI) via `my_orders` parameter in `my_account.php`
* **F-03 (Active Attack):** Time-Based Blind SQL Injection on `coupon_code` parameter (662 automated queries)
* **F-04 (Active Attack):** Webshell Execution & Outbound Connection Attempt in `/customer_images/` (`exploit.php`, `bing.php`)
* **F-05 (Active Attack):** Distributed SSH Brute Force Attack (473 failed attempts across 15+ IPs)

Artifacts:
📄 [Digital Forensics Investigation Report (Wazuh Lab)](./Blue%20Team/Wazuh%20SIEM%20Investigation%20%26%20Threat%20Hunting.pdf)

### 2. Network Security, Malware Analysis & IOC Identification

A detailed technical investigation and malware behavior analysis conducted within an isolated virtual lab environment. The project evaluates both static signatures and dynamic runtime behaviors of MSFVenom payloads (raw vs. `x86/shikata_ga_nai` polymorphic encoder) using VirusTotal, PE metadata analysis, string extraction, and the Tria.ge Automated Cloud Sandbox.

Activities performed:
* Isolated Lab Environment Setup (VirtualBox/VMware Host-Only Adapter isolation)
* Payload Generation & C2 Infrastructure Setup (MSFVenom executable generation & Metasploit multi-handler listener)
* Static Analysis & Signature Evasion Assessment (Hash calculation, VirusTotal engine comparison, PE Metadata, Entropy & Strings Analysis)
* Dynamic Sandbox Analysis (Behavioral inspection & memory unpacking via Tria.ge Sandbox)
* Indicators of Compromise (IOC) Extraction (Hashes, C2 IP/Port, Behavioral patterns, File System artifacts)
* Threat Hunting Rule Development (Custom YARA rule creation for unsigned MSFVenom Meterpreter detection)
* Incident Response Playbook Development (NIST SP 800-61 aligned containment, eradication, and recovery strategies)

Key Findings:
* **Static Evasion Limitations:** While 5 iterations of `x86/shikata_ga_nai` encoding completely mutated the file hashes (SHA-256), VirusTotal detection remained high (48/71 vs. 54/70 raw) because modern AV/EDR engines identify the decoder stub patterns.
* **Dynamic Analysis Superiority:** Tria.ge Sandbox achieved 10/10 Malicious Score for both payloads by observing in-memory unpacking and extracting exact C2 configuration (`192.168.75.128:4444`).
* **Signature vs. Behavioral Consistency:** Polymorphism alters Hash IOCs, but Network IOCs (`192.168.75.128:4444`) and Behavioral IOCs (in-memory execution & API hooking) remain constant and detectable.

Artifacts:
📄 [Malware Analysis & IOC Report](./Blue%20Team/Malware%20Analysis%20%26%20IOC%20Report.pdf)

---

## Disclaimer

All projects were conducted within authorized educational environments, laboratory platforms, or have been appropriately redacted to remove sensitive information.
