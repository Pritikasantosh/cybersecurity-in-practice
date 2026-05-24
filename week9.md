# Week 9: Incident Response Playbook & Report

## 1. Incident Overview & Scenario
* **Incident ID:** INC-2026-0524
* **Target System:** OWASP Juice Shop Web Application Container (`http://10.0.2.15:3000`)
* **Simulated Attack Vector:** SQL Injection (SQLi) authentication bypass leading to unauthorized Administrator session hijacking.
* **Framework Standard:** NIST SP 800-61 r2 (Computer Security Incident Handling Guide)

---

## 2. Phase-by-Phase Incident Response Handling

### Phase 1: Detection & Analysis
* **Detection Source:** The SIEM monitoring engine triggered a high-severity alert (`WEB_INJECTION_SQLI`) tracking a pattern match on an inbound HTTP POST request containing malicious database strings: `' OR 1=1 --`.
* **Analysis Verification:** Analysis of the application's access logs confirmed a successful `200 OK` status response immediately following the payload submission. A review of session states showed an unauthenticated external user successfully executing commands under the `admin@juice-sh.op` user identity context.

### Phase 2: Containment Strategies
* **Short-Term Containment:** The security engineer immediately issued an isolation command to separate the compromised runtime network bridge. The Docker container interface was paused to prevent any lateral network movement:
  ```bash
  sudo docker network disconnect bridge juice-shop-container
