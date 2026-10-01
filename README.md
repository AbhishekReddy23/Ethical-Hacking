# 🛠️ Vulnerable Machine Design & Penetration Testing

A Linux security project covering two perspectives: building a deliberately vulnerable machine and investigating an unfamiliar one.

Working in a three-person team, we designed a chain of misconfigurations for a controlled lab, then assessed a separate peer-built machine. The assessment followed an attack path from a vulnerable web application to root access.

[🏗️ Machine development report](Development%20of%20a%20Vulnerable%20Machine.pdf) · [🔎 Penetration-testing report](Penetration%20Testing%20on%20a%20Peer%20Machine.pdf)

## 📌 Project at a glance

| Part | Work completed |
|---|---|
| Machine development | Designed a Linux environment with six intentional weaknesses |
| Security assessment | Enumerated and tested a separate peer-built machine |
| Documented outcome | Reached root access on the assessment target |
| Deliverables | Machine-development report and penetration-testing report |

Testing took place within an authorised academic lab. The reports describe deliberately vulnerable environments.

## 🏗️ Building the vulnerable machine

We designed a sequence of weaknesses that allowed progression between Linux accounts and eventually to root. The development report explains the setup, exploitation steps, and security implications.

| Weakness | What the lab demonstrated |
|---|---|
| Weak SSH credentials | Password guessing could provide an initial foothold |
| SUID misconfiguration | An executable could cross an intended user boundary |
| Redis misconfiguration | Unrestricted file-writing operations could modify SSH authorisation |
| PATH hijacking | A privileged script could execute an attacker-controlled command |
| Unsafe Docker configuration | Privileged execution and writable host mounts could expose host accounts |
| SUID-root binary calling a writable script | Modifying a trusted script could lead to root execution |

The Docker scenario relied on unsafe configuration and host-directory access. It was not an investigation of a container-runtime zero-day.

[Read the machine development report →](Development%20of%20a%20Vulnerable%20Machine.pdf)

## 🔎 Assessing the peer machine

Our assessment began with network and service discovery, followed by investigation of a forum-style web application.

The documented attack path was:

1. **Discover the application:** Identify exposed services and enumerate web endpoints.
2. **Bypass authentication:** Confirm SQL injection in the login form.
3. **Gain code execution:** Exploit an unrestricted avatar upload to obtain a shell.
4. **Investigate local files:** Find database credentials in application source code.
5. **Recover account access:** Extract and crack a weak password hash.
6. **Reach root:** Discover additional credential material and use the recovered password.

The report includes commands, screenshots, troubleshooting steps, and an unsuccessful investigation route.

[Read the penetration-testing report →](Penetration%20Testing%20on%20a%20Peer%20Machine.pdf)

## 🛡️ Defensive lessons

The assessment showed how weaknesses across an application and its host could combine into a complete compromise.

The report discusses remediation for three key findings:

| Finding | Remediation focus |
|---|---|
| SQL injection | Parameterised database queries and safer handling of application input |
| Unrestricted file upload | Server-side validation and storage that prevents uploaded content from executing |
| Hardcoded database credentials | Secure secret storage, restricted access, and least-privilege database accounts |

These are recommendations from the assessment. The repository does not document a remediation implementation or retest.

## 🔧 Tools used

| Purpose | Tools |
|---|---|
| Network and service discovery | Nmap |
| Web resource enumeration | dirb |
| SQL injection testing | sqlmap |
| Shell access and troubleshooting | netcat, Linux utilities |
| Password testing and recovery | Hydra, John the Ripper |
| Lab development | Linux virtual machines, Redis, Docker |

## 📂 What is included

- **Development of a Vulnerable Machine.pdf** — configuration choices, intentional weaknesses, and exploitation walkthroughs.
- **Penetration Testing on a Peer Machine.pdf** — assessment methodology, findings, evidence, and remediation recommendations.

This repository contains the reports. VM images and automated environment provisioning are not included.

## 👥 Team and background

Completed by **Group 17**:

- Abhishek Reddy Gade
- Riccardo Giacinti
- Gandikota Venkata Sai Hemanth

The reports document our collective work. This project was completed for the Ethical Hacking Lab at Sapienza University of Rome.

---

[Back to my profile](https://github.com/AbhishekReddy23) · [Connect on LinkedIn](https://www.linkedin.com/in/abhishek-reddy-gade/)
