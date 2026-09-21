# Ethical Hacking Lab: Vulnerable Machine Design & Penetration Testing

**Disclaimer:** This repository and its contents are strictly for educational purposes and authorized academic testing as part of a university lab assignment. Do not use these methodologies, tools, or techniques on systems you do not own or do not have explicit, documented permission to test.

## 📌 Project Overview
This repository contains the work submitted for the Ethical Hacking Lab assignment. The project was structured to provide hands-on experience from both sides of the cybersecurity spectrum: offensive (Red Team) and defensive/design (Blue/Builder Team).

The assignment was divided into two core phases:
1. **Phase 1: Designing a Vulnerable Machine (Group 17)** - Architecting a custom Capture The Flag (CTF) style virtual machine with intentional, realistic vulnerabilities.
2. **Phase 2: Peer Penetration Testing** - Conducting a full black-box penetration test against a machine developed by another student group, documenting the attack path from initial enumeration to root compromise.

## 🏗️ Phase 1: Vulnerable Machine Development
As Group 17, we designed, configured, and deployed a custom virtual environment to challenge our peers. Our goal was to simulate real-world misconfigurations and vulnerabilities without relying on heavily automated exploits.

**Intentional Vulnerabilities Implemented:**
* **Initial Access:** SSH brute-force avenues.
* **Privilege Escalation Vectors:**
  * SUID misconfigurations
  * Redis exploitation
  * PATH variable hijacking
  * SUID-root binary abuse
  * Docker escape techniques

## ⚔️ Phase 2: Penetration Testing Methodology
We were assigned a target machine developed by a peer group. Our methodology followed standard penetration testing frameworks (e.g., PTES), covering the following phases:

1. **Reconnaissance & Enumeration:** Extensive scanning to identify active services, open ports, and hidden directories.
2. **Exploitation:** Gaining initial footholds via web vulnerabilities and misconfigured services, followed by reverse shell stabilization.
3. **Privilege Escalation:** Enumerating the local environment to identify weak permissions, leading to full `root` system compromise.

*(Note: Specific exploit scripts, passwords, and target IP addresses have been sanitized from this public repository.)*

## 🛠️ Tools & Technologies Used
* **Reconnaissance:** `nmap`, `dirb`
* **Web Exploitation:** `sqlmap`
* **Brute-Forcing & Cracking:** `Hydra`, `John the Ripper`
* **Environment:** Custom Linux Virtual Machines, Docker

## 🎓 Skills & Competencies Gained
This project reinforced both offensive techniques and system hardening principles:
* **Network & Service Enumeration:** Identifying attack surfaces across varying network protocols.
* **Web Exploitation:** Practical application of SQL Injection and file upload vulnerabilities.
* **Post-Exploitation:** Reverse shell creation, TTY stabilization, and lateral movement.
* **Advanced Privilege Escalation:** Chaining exploits including SUID/sudo abuse, PATH hijacking, Redis misconfigurations, and container escapes.
* **System Hardening:** Understanding how to secure sudoers files, Docker daemon permissions, and file access controls by exploiting them.
* **Professional Reporting:** Documenting complex attack chains clearly and collaboratively as a technical team.

## 👥 Authors
* **Group 17**
* Abhishek Reddy Gade

---
*Developed as part of the Ethical Hacking Lab Assignment.*
