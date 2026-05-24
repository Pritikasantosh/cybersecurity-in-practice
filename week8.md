# Week 8: Monitoring and Threat Detection Report

## 1. Monitoring & Architecture Overview
* **Platform Framework:** Splunk Enterprise / Elastic SIEM (Simulated)
* **Log Sources Monitored:** * Host OS Security Auditing Logs (`/var/log/auth.log`)
  * Application Container Web Server Logs (OWASP Juice Shop Access Traffic)
  * Linux Firewall Packet Event Logs (`/var/log/ufw.log`)
* **Objective:** Centralize ingestion of disparate data feeds to detect, correlate, and visualize malicious system activity.

---

## 2. SIEM Rule Correlation & Alert Configurations

To protect the lab infrastructure, two specific automated correlation rules were defined inside the SIEM analytics dashboard engine:

### Rule Alert 1: Brute Force Authentication Detection
* **Log Criteria Source:** `/var/log/auth.log` (System Authentication Module)
* **Logic Threshold Condition:** Detect greater than 10 failed login attempts (`status=failure`) targeting the same username context within a rolling 60-second window.
* **Trigger Action:** Fire a High Severity Alert: `SUSPICIOUS_BRUTE_FORCE_ATTACK_DETECTED`.

### Rule Alert 2: Web Application Injection Pattern Detection
* **Log Criteria Source:** Node.js Web Server Access Logs
* **Logic Threshold Condition:** Regex match matching known malicious string flags (e.g., `' OR 1=1 --` or `<iframe src=`) within inbound HTTP URL query strings or parameter fields.
* **Trigger Action:** Fire a Critical Severity Alert: `WEB_APPLICATION_INJECTION_ATTACK_IN_PROGRESS`.

---

## 3. Incident Investigation Dashboard Simulation

| Alert Timestamp | Detected Event Name | Source IP | Host Target | Severity | Analysis / Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `2026-05-24 08:31:02` | `WEB_INJECTION_SQLI` | `10.0.2.15` | `Juice-Shop-Container` | **Critical** | Attacker bypassed auth via `' OR 1=1 --`. System compromised. |
| `2026-05-24 08:44:15` | `FIREWALL_PORT_SCAN` | `10.0.2.15` | `Localhost Linux VM` | **Medium** | High frequency of incoming connections blocked via UFW rule matrix. |
| `2026-05-24 09:12:40` | `SUSPICIOUS_DNS_EXFIL`| `10.0.2.15` | `External Gateway` | **High** | Outbound packet requests query irregular alphanumeric subdomains. |

---

## 4. Engineering Remediations & Defensive Controls
1. **Log Forwarder Hardening:** Ensure local logging daemons utilize secure, encrypted transport layers (e.g., Syslog-over-TLS) to send data to the SIEM instance to prevent log tampering.
2. **Log Retention Framework:** Enforce explicit write-once-read-many (WORM) parameters on storage drives to guarantee that even if root access is broken into, an adversary cannot wipe historical auditing traces.
