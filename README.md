# Week 1: Introduction to Cybersecurity & Lab Setup

## 1. Basic Cybersecurity Concepts

### The CIA Triad
* **Confidentiality:** Ensuring that sensitive data is accessed only by authorized individuals. (e.g., Using encryption like AES).
* **Integrity:** Ensuring that data remains accurate and unaltered during storage or transmission. (e.g., Using cryptographic hashes like SHA-256).
* **Availability:** Ensuring that systems, networks, and applications are accessible to authorized users when needed. (e.g., Mitigating DDoS attacks).

### Key Definitions
* **Vulnerability:** A weakness or flaw in a system, software, or network design that could be exploited by a threat actor.
* **Threat:** Any potential occurrence or entity (like malware or a hacker) that intends to exploit a vulnerability to cause harm or unauthorized access.
* **Risk:** The probability or likelihood that a threat will exploit a vulnerability, combined with the resulting operational or financial impact.

---

## 2. Lab Environment Setup

### Components
* **Host OS:** Windows 10/11
* **Hypervisor:** Oracle VirtualBox
* **Attacker Machine:** Kali Linux (Debian 64-bit, 2GB RAM, 2 vCPUs)
* **Vulnerable Target:** OWASP Juice Shop

### Pre-installed Security Tools Used
* **Wireshark:** Used for network packet analysis and sniffing traffic.
* **Burp Suite:** Used as an interception proxy for web application security testing.
