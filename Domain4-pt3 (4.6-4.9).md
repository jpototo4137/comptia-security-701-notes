# 4.6 Identity and Access Management (IAM)

---

## IAM Basics
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Provisioning / Deprovisioning** | Creating/removing user accounts | New hire/termination processes | Q: Admin offboards user, which IAM function? |
| **Permission Assignment** | Limit user’s access | Ensure least privilege | Q: Which IAM principle ensures minimum required rights? |
| **Identity Proofing** | Validating user identity | High-security environments | Q: Before granting remote access, verify user identity – which process? |

---

## Authentication / Authorization
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **SSO (Single Sign-On)** | One login → access multiple resources | Enterprise apps (email, SharePoint, etc.) | Q: User logs in once, gains access to multiple systems. What is this? |
| **Federation** | Share authentication across orgs | Partner companies, “Login with Google” | Q: User logs in with FB credentials on another site – which concept? |

---

## Protocols / Standards
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **LDAP** | Directory access protocol | Querying Active Directory, enterprise networks | Q: Protocol used to access X.500 directory? |
| **SAML** | XML-based auth/authorization standard | SSO in enterprise web apps | Q: Which standard lets users authenticate once and use multiple web apps? |
| **OAuth** | Authorization framework | Third-party API access (what user can do) | Q: Which framework allows app A to access app B’s resources without sharing password? |
| **OpenID Connect** | Authentication layer on top of OAuth | Sign-in with Google / OIDC tokens | Q: Which adds authentication to OAuth? |

---

## Access Control Models

| Model | Description | Analogy | When to Use | Exam Scenario |
|-------|-------------|---------|-------------|---------------|
| **MAC** | Mandatory Access Control: Labels + clearance levels. | Military “Top Secret” clearance. | Gov/military, highly secure data. | “User cannot change perms, system enforces labels.” |
| **DAC** | Discretionary Access Control: Owner decides who gets access. | Windows folder “Right click → Share.” | Most common in OS (Windows, Unix). | “File owner grants or changes permissions.” |
| **RBAC** | Role-Based Access Control: Permissions tied to roles/groups. | HR group auto gets HR docs. | Large orgs, scalability. | “Finance team gets finance system.” |
| **Rule-based** | System-enforced rules (ACLs, firewall-like). | If/else conditions. | Network/firewall style enforcement. | “Access only if time=9AM–5PM.” |
| **ABAC** | Attribute-Based Access Control: Multiple factors (role, IP, time, location). | Cloud fine-grained policy. | Modern cloud & zero trust. | “User must be in HR role, using corp IP, during work hours.” |

---

## Security Principles
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Least Privilege** | Minimum required rights | Everywhere | Q: Which principle states accounts should have only required permissions? |
| **Time-of-Day Restrictions** | Block access by time | Reduce risk after hours | Q: Policy blocks DB access between midnight–6am, what is this? |

---

## Multifactor Authentication (MFA)
| Factor | Example | When to use | Exam scenario |
|--------|---------|-------------|---------------|
| **Something you know** | Password, PIN | Always baseline | User logs in with password |
| **Something you have** | Token, SMS code | Extra login security | Admin uses smart card |
| **Something you are** | Fingerprint, iris | High security | Biometric scan at door |
| **Somewhere you are** | IP, GPS | Geofencing, remote work | Access only allowed in HQ |

---

## Password Concepts
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Best practices** | Complexity, length, expiration | All users | Q: Which improves password security? |
| **Password managers** | Store securely in DB | User convenience | Q: Which allows secure storage of multiple creds? |
| **Passwordless** | Biometrics, security keys | Modern apps, mobile | Q: Face ID login – which method? |

---

## Privileged Access Management (PAM)
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Just-in-Time Access** | Temporary admin rights | Admin tasks, reduce attack surface | Q: Admin gets temp rights for 1 hour – which concept? |
| **Password Vaulting** | Store root/admin creds in vault | High-security IT ops | Q: Which stores and controls access to privileged accounts? |
| **Ephemeral Credentials** | Disposable credentials | Cloud access, temp accounts | Q: Admin gets creds valid for one session – which? |


# 🔑 Identity and Access Management (IAM) Big Picture Cheat Sheet

---

## 🚀 IAM (Identity & Access Management)
- **What:** Framework for identities + access.  
- **When to use:** Always, any org with employees/devices/apps.  
- **Why:** Prevents chaos (no “everyone is admin”).  
- **Analogy:** Security badges in a building.  
- **Exam clue:** Provisioning, SSO, account lifecycle → **IAM**.

---

## 🔐 MFA (Multi-Factor Authentication)
- **What:** More than 1 proof of identity (password + code, fingerprint + card).  
- **When to use:** Sensitive accounts (admins, VPN, banking, cloud).  
- **Why:** Stops stolen password attacks.  
- **Analogy:** Apartment key + fingerprint scanner.  
- **Exam clue:** Scenario about “reduce password attacks” → **MFA**.

---

## 👑 PAM (Privileged Access Management)
- **What:** Special handling for **admin/root** accounts.  
- **When to use:** IT staff, cloud admins, privileged users.  
- **Why:** If admin hacked → attacker owns everything.  
- **Features:**  
  - Just-in-Time (temporary rights)  
  - Vaulting (store admin creds, no one sees them)  
  - Ephemeral creds (self-destruct after use)  
- **Analogy:** Master key melts after 1 hr use.  
- **Exam clue:** “Temporary elevated rights / admin account risk” → **PAM**.

---

## 🗂️ Access Control Models
| Model | Description | Analogy | Exam Scenario |
|-------|-------------|---------|---------------|
| **MAC** | Mandatory labels & clearance | Military clearance | “Top Secret file” |
| **DAC** | Owner decides access | Windows folder “Share” | “File owner gives perms” |
| **RBAC** | Based on role/job group | HR group gets HR files | “Finance team access” |
| **Rule-based** | System-enforced rules | Firewall ACLs | “If/else conditions” |
| **ABAC** | Multi-criteria (location, IP, time) | Cloud fine-grained | “Time-based or location-based access” |

---

## 📡 IAM Protocols & Standards

| Protocol/Standard | What it does | Analogy | When/Exam use |
|-------------------|-------------|---------|---------------|
| **LDAP** | Directory protocol for users/groups | Company phonebook | “Query user DB” |
| **SAML** | Web SSO standard (XML) | Passport for web apps | “Enterprise SSO” |
| **OAuth** | Delegated access (authorization) | Giving valet keys | “Grant access without password” |
| **OpenID Connect** | Identity/auth on top of OAuth | “Sign in with Google” | “Auth built on OAuth” |

---

# 📝 TL;DR Exam Strategy
- **IAM** = Whole framework (accounts, lifecycle, SSO).  
- **MFA** = Stop password-only hacks.  
- **PAM** = Protect admin/root accounts.  
- **Access models** = Philosophies (MAC, DAC, RBAC, ABAC).  
- **LDAP/SAML/OAuth/OIDC** = Protocols that *make IAM work in real life*.


## 4.7 Automation and Orchestration

### 🔹 Scripting & Automation

**Benefits / Pros**
- Automate & orchestrate repetitive security tasks  
- Speed → faster reaction to incidents  
- Save time → workforce multiplier (scripts run 24/7)  
- Enforce baselines (e.g., missing patch auto-installed)  
- Consistency → standardized infrastructure configs (firewall rules, IP configs, etc.)  
- Secure scaling (cloud/VMs auto-hardened when deployed)  
- Improves employee retention → less burnout from repetitive tasks  

---

### 📌 Common Use Cases

| Use Case | What It Does | Security Value | Exam Relevance |
|----------|--------------|----------------|----------------|
| **User & Resource Provisioning** | Auto create/remove accounts during onboarding/offboarding | Prevents orphaned accounts (insider threat) | *“Automate account provisioning” → answer is automation/orchestration* |
| **Guard Rails** | Automated checks/validations for configs | Prevents misconfigurations | *“Automated policy validation” → guard rails* |
| **Security Groups** | Assign/remove group access, constant audits | Enforces least privilege | *“Auto group assignment” → automation* |
| **Ticket Creation** | Auto-generate helpdesk/security tickets | Faster incident tracking | SIEM + SOAR combo in practice |
| **Escalation** | Auto correct issues before human involvement | Saves analyst time | *“Scripted escalation before analyst review”* |
| **Controlling Services/Access** | Enable/disable services automatically | Reduces attack surface | E.g., auto-disable unused ports |
| **Continuous Integration / Testing** | Automate security testing during build pipelines (CI/CD) | DevSecOps integration | Exam may mention “secure CI/CD pipeline” |
| **API Integration** | Connect tools (SIEM, SOAR, NAC, firewalls) via APIs | Orchestration across multiple platforms | *Keyword: API-driven automation* |


- **Guard rails**: 
are used by application developers to provide a set of
automated validations to user input and behavior. Guard rails are not used
by the help desk team

- **Escalation**: 
Automation can recognize security events and escalate a security-related
ticket to the incident response team without any additional human
interaction.

### Automation vs Orchestration vs SOAR

| Concept | What It Means | Scope | Example | Exam Scenario |
|---------|---------------|-------|---------|---------------|
| **Automation** | Single task executed by a script/tool | Narrow, task-level | Auto-disable unused account | “System auto-applies patches without admin input” |
| **Orchestration** | Linking multiple automated tasks across systems | Broader, workflow-level | Auto-create account → assign groups → send ticket → configure access | “Coordinated response across IAM, SIEM, firewall” |
| **SOAR** (Security Orchestration, Automation & Response) | Platform that combines orchestration + automation + case management | Enterprise-wide | SIEM alert → SOAR auto-triggers block on firewall → opens ticket | “Integrates SIEM alerts with automated remediation” |

Big Picture:
	•	Automation = “one button does one thing.”
	•	Orchestration = “connect multiple buttons together into a flow.”
	•	SOAR = “full platform for orchestration + automation + incident response.”

On the exam, if they ask about “single repetitive task” → Automation.
If it’s “end-to-end process across multiple tools” → Orchestration.
If it’s “security alerts auto-handled and tracked” → SOAR.

---

### ⚠️ Scripting Considerations

| Concern | Meaning | Risk |
|---------|---------|------|
| **Complexity** | Scripts become hard to manage | More prone to bugs |
| **Cost** | Development & maintenance overhead | Budget issues |
| **Single Point of Failure** | If automation breaks, critical tasks stop | Reliability risk |
| **Technical Debt** | Old scripts not updated over time | Security holes |
| **Ongoing Supportability** | Needs continuous updates | Long-term management load |

---

### Big Picture
- **Automation = do tasks faster/consistent**  
- **Orchestration = link multiple systems/tools together via automation** (like SOAR + APIs).  
- Together, they:  
  - Reduce human error  
  - Speed up incident response  
  - Free humans for analysis, not repetitive work
 

# 4.8 Incident Response  

## Incident Response Process (NIST SP 800-61)  

1. **Preparation**  
   - Policies, plans, playbooks, tools  
   - Training staff for incidents  

2. **Detection & Analysis**  
   - Identify suspicious activity (logs, alerts, anomalies)  
   - Confirm whether it’s an actual incident  

3. **Containment, Eradication & Recovery**  
   - **Containment**: prevent spread (segmentation, disable accounts)  
   - **Eradication**: remove malware, disable breached accounts, fix vulnerabilities  
   - **Recovery**: restore systems, rebuild from clean backups  

4. **Lessons Learned**  
   - Post-incident review  
   - What went wrong, what worked well  
   - Update training & playbooks  

---

## Incident Planning  

| Concept              | Description | Example | Exam Tip |
|----------------------|-------------|---------|----------|
| **Training** | Staff must be prepared to follow IR plan | Phishing awareness, incident playbooks | Expect scenario: *“Which step ensures staff knows what to do during IR?”* |
| **Tabletop Exercise** | Discussion-based, walk through response | “What if ransomware hit our file server?” | Low cost, good for logistics |
| **Simulation** | Hands-on, real-time mock attack | Red team vs Blue team exercise | More realistic, resource heavy |
| **Root Cause Analysis** | Identify *true* cause of incident | Patch missing → exploit occurred | Exam Q: “What analysis identifies ultimate cause?” |
| **Threat Hunting** | Proactive search for attackers | Look for unusual logins, beaconing | Needed because threat intel is **reactive** |

---

## Digital Forensics  

**Goal:** Collect, preserve, and analyze evidence from incidents  

### Core Principles  
- **RFC 3227** – Evidence Collection best practices  
- **Process:** Acquisition → Analysis → Reporting  

### Key Forensic Concepts  

| Term | Description | Example | Exam Tip |
|------|-------------|---------|----------|
| **Legal Hold** | Preserve data for litigation, initiated by legal | Custodian told not to delete emails | Triggered by legal counsel |
| **Chain of Custody** | Document evidence handling to maintain integrity | Hashing a hard drive before transfer | Integrity check, no tampering |
| **Acquisition** | Collect evidence (disk, RAM, logs, snapshots) | Capture volatile memory first | Order of volatility is exam favorite |
| **Preservation** | Secure storage and handling of evidence | Sealed and tagged evidence drive | Prevents loss or corruption |
| **Reporting** | Summarize findings, explain methodology | IR summary for management | Must be clear and defensible |
| **E-Discovery** | Legal process to collect/review electronic docs | Search emails in fraud case | Often paired with forensics |

---

## Quick Comparisons  

### Tabletop vs Simulation  

| Type | Approach | Cost | Use Case |
|------|----------|------|----------|
| **Tabletop** | Discussion, “what-if” scenarios | Low | Plan review & logistics |
| **Simulation** | Realistic, hands-on attack | High | Full readiness test |

---

### Legal Hold vs Chain of Custody  

| Concept | Purpose | Who Initiates | Exam Keyword |
|---------|---------|---------------|--------------|
| **Legal Hold** | Preserve data for legal reasons | Legal Counsel | Litigation trigger |
| **Chain of Custody** | Maintain integrity of evidence | Security/Forensic Team | Integrity, tampering |

---

### *Order of Volatility (Exam Must-Know)  
1. CPU registers, cache  
2. RAM  
3. Network traffic  
4. Disk  
5. Backups/archives  

---

**Exam Angle:**  
- Questions will often ask: *“What’s the FIRST step after detecting malware?”* → **Containment**  
- Or: *“Which evidence should be collected first?”* → **RAM (order of volatility)**  
- Or: *“Legal team requires preservation of data for court, what’s this called?”* → **Legal Hold**  




# Digital Forensics – Bigger Picture  

## What is Digital Forensics?  
Digital forensics is the **practice of investigating digital systems after an incident**.  
- **Collect → Preserve → Analyze → Present** digital evidence.  
- Think of it as **crime scene investigation for IT**.  

---

## Why do we need it?  
1. **Find the truth** – what happened, how, when, by whom.  
2. **Recover from incidents** – identify root cause and stop attackers from returning.  
3. **Compliance/legal** – many industries require evidence to be handled properly.  
4. **Accountability** – show customers, regulators, and courts that your response was correct.  
5. **Future defense** – lessons learned strengthen security posture.  

---

## Why the key concepts exist  

| Concept | Big Picture Purpose | If Ignored → Problem |
|---------|----------------------|-----------------------|
| **Legal Hold** | Freeze relevant data so it’s not deleted during a lawsuit. | Critical emails/logs vanish → company fined, case lost. |
| **Chain of Custody** | Proves evidence wasn’t tampered with. Tracks who handled it, when, and how. | Evidence thrown out in court. |
| **Acquisition** | Method of collecting data (disk, RAM, logs) in a verifiable way. | Evidence corrupted or incomplete. |
| **Preservation** | Protects evidence for long-term use. | Data loss, altered files. |
| **Reporting** | Documents findings in a clear, defensible way. | No one can trust or act on the results. |
| **E-Discovery** | Supplies electronic documents for lawsuits. | Legal penalties for not producing required info. |

---

## Example: Ransomware Attack  
- **IR (incident response)**: stops attack & restores from backup.  
- **Forensics steps in**:  
  - Collect RAM + logs to see attacker activity.  
  - Preserve drives for evidence.  
  - Chain of custody ensures trust.  
  - Reporting documents exactly what happened.  
  - Legal hold & e-discovery triggered if lawsuits/regulators get involved.  

---

## Exam Big Picture (Security+)  
- **IR = contain & recover**.  
- **Forensics = investigate & prove**.  
- Exam questions love:  
  - “What ensures evidence can be used in court?” → **Chain of custody**  
  - “What prevents deletion of relevant data during litigation?” → **Legal hold**  
  - “Which evidence is collected first?” → **RAM (order of volatility)**  

---

In short:  
**Digital forensics = trust + accountability.**  
Without it, evidence is unreliable, companies can’t defend themselves, and attackers keep coming back.  

# 4.9 Security Data Sources

## Purpose
- **Support investigations** by gathering **evidence from multiple sources**.  
- Detect attacks, validate incidents, and correlate across systems.  
- Security+ exam often shows you a **log snippet** → you must **extract the key info** (IP, time, user, attack type).

---

## Log Data (Where to Look)

| Source | What It Shows | Why It Matters (Exam Use) |
|--------|---------------|---------------------------|
| **Firewall Logs** | Allowed/blocked traffic, source/destination IP, port, disposition, URL categories (NGFW). | Identify malicious inbound/outbound traffic. |
| **Application Logs** | App-specific (Windows Event Viewer, Linux `/var/log`). | Detect failures, privilege escalation, misused apps. |
| **Endpoint Logs** | Logins, system events, processes, account mgmt. | Spot malware on endpoints, correlate with SIEM. |
| **OS Security Logs** | Auth attempts, file changes, brute force detection. | Exam loves brute-force detection or failed logins. |
| **IPS/IDS Logs** | Attack signatures, timestamp, src/dst IP & port. | Detect known exploits; confirm intrusion attempts. |
| **Network Device Logs** | Switch/router/AP/VPN logs, routing/auth issues. | Track lateral movement or VPN login abuse. |
| **Security Logs** | Blocked traffic, DNS sinkhole, exploit attempts. | Shows “big picture” threats. |

---

## Other Data Sources

| Source | Description | Why It Matters |
|--------|-------------|----------------|
| **Metadata** | Data about data (e.g., email headers, phone GPS, device type). | Traces origin of messages/files. |
| **Vulnerability Scans** | Finds missing controls, misconfigs, exposed services. | Proactive detection before attacker exploits. |
| **Automated Reports** | Prebuilt SIEM reports. | Saves time, but humans must interpret. |
| **Dashboards** | Real-time summary view. | Best for live monitoring, not historical analysis. |
| **Packet Captures (PCAP)** | Raw packet data, often Wireshark. | Troubleshoot unknown traffic, verify filtering. |

---

## Exam Tip: Reading Logs

### Firewall log

DENY TCP 203.0.113.50:443 → 10.0.0.5:3389

- Outbound traffic from server → RDP (3389). Likely malware.

### IDS log

[ALERT] SQL Injection attempt from 192.168.1.10 to 10.0.0.25

- Attacker IP is inside (insider threat).

### Authentication log

Failed login attempt - user: admin from 10.0.0.77

- Brute force suspected.

👉 Exam questions will often ask **“what is the MOST likely source of this log?”** or **“which log would you check to confirm this?”**

---

## 🔎 Big Picture
- **Logs are the breadcrumbs.**  
  - IR tells you **what happened**.  
  - Forensics proves **who, when, how**.  
  - Logs are the **raw evidence** that tie it all together.  

- Security+ focus:  
  - Know **which log/source** is appropriate.  
  - Recognize **suspicious entries**.  
  - Understand **how to correlate multiple logs** in SIEM.  
