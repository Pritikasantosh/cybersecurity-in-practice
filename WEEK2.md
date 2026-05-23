# Week 2: Threat Modeling Report

## 1. Threat Modeling Overview
* **Target Application:** OWASP Juice Shop (Web Application)
* **Framework Used:** STRIDE Model
* **Objective:** Identify potential entry points, vulnerabilities, and required security controls for the web application setup.

---

## 2. STRIDE Threat Analysis & Security Controls

### 1. Spoofing (Authentication Violation)
* **Threat Scenario:** An attacker intercepts or guesses user credentials to log into a customer account or administrative account.
* **Security Control / Mitigation:** Implement strong password hashing (e.g., bcrypt), enforce complex password policies, and implement Multi-Factor Authentication (MFA).

### 2. Tampering (Integrity Violation)
* **Threat Scenario:** An attacker alters the HTTP request parameter values (like changing the quantity or price of a product in the shopping cart before checkout).
* **Security Control / Mitigation:** Perform strict server-side validation for all input data and transaction details; do not rely on client-side constraints.

### 3. Repudiation (Non-Repudiation Violation)
* **Threat Scenario:** A user modifies another customer's data or deletes store items, and administrators cannot track who did it due to a lack of system logs.
* **Security Control / Mitigation:** Implement comprehensive, centralized logging (recording user IDs, timestamps, and actions performed) and protect log files with read-only permissions.

### 4. Information Disclosure (Confidentiality Violation)
* **Threat Scenario:** The application displays detailed SQL error messages on the screen or leaks private customer addresses via API responses.
* **Security Control / Mitigation:** Disable detailed error debugging pages in production. Enforce data encryption in transit using HTTPS (TLS/SSL).

### 5. Denial of Service (Availability Violation)
* **Threat Scenario:** An attacker uses a tool to flood the Juice Shop application login page with thousands of requests per second, causing the container to crash.
* **Security Control / Mitigation:** Use rate limiting on the web server, implement CAPTCHAs on authentication forms, and use a Web Application Firewall (WAF).

### 6. Elevation of Privilege (Authorization Violation)
* **Threat Scenario:** An unauthenticated visitor manually types `/the-key-to-the-secret-admin-page` into the browser URL bar and successfully accesses the administration panel.
* **Security Control / Mitigation:** Implement strict Role-Based Access Control (RBAC). The server must validate authorization privileges on every single request, not just hide the UI buttons.
