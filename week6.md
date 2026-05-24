Week 6: Penetration Testing Basics Report

## 1. Engagement Overview
* **Target Host Configuration:** OWASP Juice Shop App Container (`http://10.0.2.15:3000`)
* **Testing Platform Engine:** Kali Linux VM (VirtualBox Environment)
* **Primary Exploitation Engine Tool:** Metasploit Framework (MSFconsole v6.x)
* **Objective:** Simulate an authorized, tactical exploit sequence targeting application infrastructure dependencies to demonstrate system compromise risks.

---

## 2. Simulated Attack Execution Workflow

### Phase 1: Service Reconnaissance
A tactical port scan verification was initiated to confirm active attack surfaces. Port `3000/TCP` was verified as open and executing an active Node.js express web runtime architecture.

### Phase 2: Exploitation Strategy & Module Selection
* **Selected Metasploit Module:** `exploit/multi/http/node_js_exec`
* **Payload Type Configuration:** `linux/x64/meterpreter/reverse_tcp`
* **Target Configuration Parameters:**
  * `RHOSTS` (Remote Host Target): `10.0.2.15`
  * `RPORT` (Remote Port Target): `3000`
  * `LHOST` (Local Attacker Listening Host IP): `10.0.2.15`

### Phase 3: Exploitation Vector Analysis
The attack vectors model targets a simulated injection vulnerability within the back-end application container parsing logic. By packaging an asynchronous command string execution payload inside the incoming HTTP headers, the application processes the vector string into an active system command run.

---

## 3. Post-Exploitation Analysis & Impact
* **Access Level Achieved:** Local Container User Privilege Command Shell.
* **Operational Risk Impact:** High/Critical. A successful attack sequence completely compromises system data confidentiality, allowing an adversary to read application source files, dump internal session keys, and pivot across adjacent backend network database pools.

---

## 4. Engineering Remediations & Technical Controls
1. **Apply Strict Input Validation:** Filter and sanitize all user-supplied input data strings before processing parameters inside dynamic application runtime loops.
2. **Container Security Hardening:** Enforce strict rootless container isolation profiles. Ensure that even if an execution exploit succeeds, the shell process runs under a minimal-privilege guest daemon profile, blocking host-level breakout access.
