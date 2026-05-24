# Practical Cybersecurity Internship Portfolio

Welcome to my security engineering project repository. This repository serves as a comprehensive documentation portfolio tracking a 10-week hands-on technical internship focused on infrastructure setup, application security assessments, defensive hardening, and threat monitoring.

## 🛠️ Environment Blueprint
* **Host Hypervisor:** Oracle VirtualBox v7.x
* **Attack Platform:** Kali Linux Rolling Distribution
* **Target Environment:** Docker Container Architecture hosting OWASP Juice Shop
* **Defensive Controls:** Uncomplicated Firewall (UFW), System Auditing Daemons

---

## 📈 Weekly Executive Milestones & Deliverables

This portfolio is systematically organized into clear, dedicated reporting matrices detailing specific technical objectives, testing workflows, and remediation playbooks:

### 🔹 Module 1: Core Fundamentals & Lab Deployment
Initial architectural provisioning of safe, isolated virtualization boundaries. 
* 📑 **Detailed Report:** [README.md](./README.md) *(or reference your introductory logs)*

### 🔹 Module 2: Threat Modeling & Surface Mapping
Deconstruction of target applications utilizing structured security parameters to identify high-risk logical data boundaries.
* 📑 **Detailed Report:** [WEEK2.md](./WEEK2.md)

### 🔹 Module 3: Web Application Penetration Testing
Manual exploitation vectors executed against local interfaces, highlighting severe programmatic flaws.
* 🛠️ **Core Findings:** Successful validation of SQL Injection (Authentication Bypass) and Reflected Cross-Site Scripting (XSS).
* 📑 **Detailed Report:** [WEEK3.md](./WEEK3.md)

### 🔹 Module 4: Network Traffic Capture & Protocol Analysis
Live monitoring of network interfaces to trace interaction boundaries and detect malicious traffic indicators.
* 🛠️ **Core Findings:** Isolated malicious DNS queries using explicit packet filter controls.
* 📦 **Raw Artifact Included:** `week4_network_analysis.pcap`
* 📑 **Detailed Report:** [WEEK4.md](./WEEK4.md)

### 🔹 Module 5: Automated Vulnerability Assessment
Scaling defensive testing frameworks using automated scanning tools to trace outdated host dependencies and configurations.
* 📑 **Detailed Report:** [WEEK5.md](./WEEK5.md)

### 🔹 Module 6: Framework Exploitation & Attack Simulation
Utilizing advanced validation frameworks to simulate tactical system compromise and evaluate post-exploitation risk impact.
* 🛠️ **Core Tooling:** Metasploit Console Framework (`msfconsole`)
* 📑 **Detailed Report:** [WEEK6.md](./WEEK6.md)

### 🔹 Module 7: Local Host System Hardening
Transitioning to tactical defense by configuring zero-trust boundaries directly within the host kernel.
* 🛠️ **Core Controls:** Implementation of a strict default-deny host firewall (UFW tracking port `3000/tcp`).
* 📑 **Detailed Report:** [WEEK7.md](./WEEK7.md)

### 🔹 Module 8: Security Information & Event Management (SIEM)
Centralizing system logs to build rule-based correlation alerts capable of identifying automated attack signatures.
* 📑 **Detailed Report:** [WEEK8.md](./WEEK8.md)

### 🔹 Module 9: Incident Response Planning & Playbooks
Establishing a clear incident recovery pipeline aligned directly with professional NIST standards.
* 🛠️ **Core Strategies:** Playbooks outlining containment via container isolation and micro-perimeter firewall blocks.
* 📑 **Detailed Report:** [WEEK9.md](./WEEK9.md)

---

## 🏁 Professional Summary & Takeaways
This internship program successfully bridged theoretical principles with engineering application. By stepping through the entire cycle—from initially scanning a system, identifying structural vulnerabilities, exploiting them to prove risk, implementing local firewalls, and logging incidents—I have established a comprehensive understanding of both offensive red-team tactics and defensive blue-team systems operations.
