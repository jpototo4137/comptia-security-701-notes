# Security+ Cheatsheet

Quick reference sheet for key concepts and categories in CompTIA Security+ (SY0-701). 
This is a living document and will be updated as I progress through each domain.

---

###### Security Control Categories & Functional Types - Cheatsheet  

*Keywords but context matters! (can fit into multiple types)*  

---

**Managerial:**  
Policies & Procedures → planning & assessment methods  

**Technical:**  
Hardware/software → tech  

**Operational** (new in SY0-701):  
Ensure day-to-day operations by **people** (not systems)  

**Physical:**  
Facility / real-world objects → tangible (touchable)  

---

- **Deterrent** (discourage/violation): warning sign, visibility, perception  
- **Preventive** (stop): access control, authentication, firewall, encryption  
- **Directive** (direct, confine/control): policy, procedure, standard, guideline  
- **Detective** (discover/detect): monitoring, audit, logging, alert  
- **Corrective** (restore): backup, restore, incident response, patching  
- **Compensating** (provide options): alternative, backup, redundancy  

---

### ☁️ Cloud Service & Deployment Models – Cheatsheet

---

#### Cloud Service Models  
_(Ranked by control: high → low)_

| Model | User Responsibility | CSP Responsibility | Notes |
|-------|----------------------|---------------------|-------|
| **IaaS**<br>(Infrastructure as a Service) | VMs, virtual networks, guest OS security | Physical hardware, network, storage, virtualization | ✅ Most control, most complex |
| **PaaS**<br>(Platform as a Service) | App configuration & logic | OS, runtime, middleware, infrastructure | ⚙️ Easier, but limited control |
| **SaaS**<br>(Software as a Service) | Access control, feature settings, data recovery | Everything else (infra, app, availability) | 🧼 Simplest, least control |

---

#### Shared Responsibility Model (User vs. Cloud Provider)

- **IaaS** → You manage: OS, data, app config  
- **PaaS** → You manage: app config & data  
- **SaaS** → You manage: access & some settings  
- Everything else is the **Cloud Service Provider (CSP)**’s job

Tip: Responsibility shifts **more to the CSP** as you go from IaaS → SaaS.

---

#### Cloud Deployment Models

| Model | Description | Use Case |
|-------|-------------|----------|
| **Public Cloud** | Entirely on provider's hardware | Scalable, no maintenance, cost-efficient |
| **Private Cloud** | Hosted on-premises or for one org | Compliance, legacy systems |
| **Hybrid Cloud** | Mix of public + private | Gradual migration, flexibility |
| **Community Cloud** | Shared among related orgs | Same sector, shared security goals |
| **Multi-Cloud** | Uses multiple public cloud providers | Cost control, vendor flexibility (more complex) |

---
#### Vuln Management

🔹 SAST (Static Application Security Testing)
	•	When: during development phase (before deployment).
	•	Why: to catch coding flaws early → buffer overflows, injections.
	•	Scenario keyword: “developer needs to check code for vulnerabilities before running it” → use SAST.
	•	Limit: can’t test runtime issues (auth, crypto). Produces false positives.

⸻

🔹 Fuzzing (Dynamic Analysis)
	•	When: during testing phase, after code compiles and runs.
	•	Why: test how the application reacts to unexpected/random inputs.
	•	Scenario keyword: “looking for crashes, errors, exceptions” → fuzzing.
	•	Limit: resource heavy, not efficient for every scenario.

⸻

🔹 Package Monitoring
	•	When: during software acquisition and deployment.
	•	Why: to ensure downloaded packages (libraries, updates, dependencies) are from trusted sources and contain no hidden malware/vulnerabilities.
	•	Scenario keyword: “developer installs library from untrusted repo” → check with package monitoring.
	•	Limit: Doesn’t test the code, only verifies source integrity.

⸻

🔹 Penetration Testing
	•	When: after systems are deployed, in production environments (not just dev/test).
	•	Why: simulate real attacker behavior to confirm exploitable vulnerabilities.
	•	Scenario keyword: “organization must validate if a vulnerability can be exploited” → pentest.
	•	Notes:
	•	Required by compliance (PCI DSS, HIPAA).
	•	Rules of engagement define scope.
	•	Risks: may cause DoS/data loss.


#### 4.4 Security Monitoring
 
| **Name**              | **Category**         | **Notes** |
|------------------------|----------------------|-----------|
| **SCAP**              | Framework/Standard   | NIST-managed automation/compliance |
| **Benchmarks (CIS)**  | Framework/Standard   | Baseline best practices |
| **Agents vs Agentless** | Concept            | Data collection approach |
| **Log aggregation / quarantine** | Concept  | Monitoring activities |
| **SIEM**              | Tool/System          | Collects, correlates, alerts, forensics |
| **DLP**               | Tool/System          | Prevents sensitive data leaks |
| **Antivirus/Anti-malware** | Tool/Software   | Detects and removes malware |
| **Vulnerability scanner** | Tool/System      | Detects flaws, not exploitation |
| **SNMP**              | Protocol             | Device monitoring (MIB/OIDs, polling on UDP/161) |
| **SNMP Traps**        | Protocol Function    | Device-initiated alerts (UDP/162) |
| **NetFlow**           | Protocol/Standard    | Collects traffic flow metadata (probe/collector) |


	•	If they ask about endpoint compliance monitoring → think agent/agentless, SCAP.
	•	If they ask about log aggregation/correlation → think SIEM.
	•	If they ask about network device stats → think SNMP / SNMP traps.
	•	If they ask about network traffic patterns → think NetFlow.
	•	If they ask about preventing data leaving → think DLP.


 
#### Frequently Asked Ports 

| **Service**         | **Port (TCP/UDP)** | **Notes** |
|----------------------|--------------------|-----------|
| **FTP (control/data)** | 21 (control), 20 (data) | Insecure → use SFTP/FTPS |
| **SSH / SFTP / SCP** | 22 | Secure remote login/file transfer |
| **Telnet**           | 23 | Insecure remote login |
| **SMTP**             | 25 | Mail transfer (unencrypted) |
| **DNS**              | 53 TCP/UDP | TCP for zone transfers, UDP for queries |
| **DHCP**             | 67 (server), 68 (client) | Auto IP assignment |
| **TFTP**             | 69 | Trivial FTP, insecure |
| **HTTP / HTTPS**     | 80 / 443 | Web traffic |
| **POP3 / POP3S**     | 110 / 995 | Email retrieval |
| **IMAP / IMAPS**     | 143 / 993 | Email retrieval with folders |
| **SNMP**             | 161/162 UDP | 161 = polling, 162 = traps |
| **LDAP / LDAPS**     | 389 / 636 | Directory services |
| **SMB / CIFS**       | 445 | File sharing (Windows) |
| **Syslog**           | 514 UDP | Log forwarding |
| **RDP**              | 3389 | Remote desktop |
| **NTP**              | 123 UDP | Time sync |
| **Kerberos**         | 88 | Authentication protocol |


| **Role**                   | **Key Functions**                                            |
| -------------------------- | ------------------------------------------------------------ |
| **Data Owner**             | Final authority, legally responsible, often exec-level       |
| **Data Steward**           | Ensures data meaning, rules, and usage are known             |
| **Custodian**              | IT role, implements protection (CIA, logs, backups) → *day-to-day* handler |
| **Data Controller (GDPR)** | Decides how/why data is processed                            |
| **Data Processor (GDPR)**  | Processes data on behalf of controller                       |
| **Data Subject (GDPR)**    | The individual whose data is collected (e.g., customer)      |

🔎 *“Day-to-day” = custodian* (EXAM!)
