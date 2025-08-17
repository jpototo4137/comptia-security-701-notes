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


**Data Roles**

| **Role**                   | **Key Functions**                                            |
| -------------------------- | ------------------------------------------------------------ |
| **Data Owner**             | Final authority, legally responsible, often exec-level       |
| **Data Steward**           | Ensures data meaning, rules, and usage are known             |
| **Custodian**              | IT role, implements protection (CIA, logs, backups) → *day-to-day* handler |
| **Data Controller (GDPR)** | Decides how/why data is processed                            |
| **Data Processor (GDPR)**  | Processes data on behalf of controller                       |
| **Data Subject (GDPR)**    | The individual whose data is collected (e.g., customer)      |

🔎 *“Day-to-day” = custodian* (EXAM!)

| **Policy**                      | **Purpose/Example**                                          |
| ------------------------------- | ------------------------------------------------------------ |
| **AUP (Acceptable Use Policy)** | Defines what users can/can’t do with company IT (e.g., no social media at work) |
| **Information Security Policy** | Org-wide security goals and direction                        |
| **Business Continuity Policy**  | Keep operations running during disruptions                   |
| **Disaster Recovery Policy**    | Focused on recovery after disaster or attack                 |
| **Incident Response Policy**    | High-level response framework for cyber incidents            |
| **SDLC Policy**                 | Security integration into software development lifecycle     |
| **Change Management**           | Control risks when changing systems                          |



| **Standard**      | **What it Covers**                               |
| ----------------- | ------------------------------------------------ |
| **NIST/CIS**      | Password policies, benchmarks                    |
| **ISO 27001**     | ISMS (Info Sec Management System)                |
| **FIPS 140-2/3**  | Federal-level encryption requirements            |
| **NFPA/ANSI/ISO** | Physical security (access badges, HVAC, cameras) |


# Risk Management Exam Key Terms & Triggers

---

## Risk Response Techniques

| Term        | Definition / Use                                                                 | Exam Keywords / Indicators | Scenario |
|-------------|----------------------------------------------------------------------------------|----------------------------|----------|
| **Mitigate** | Implement controls to reduce risk (but some residual risk remains)              | "countermeasure", "reduce risk", "implement control" | Install firewall, patch system |
| **Transfer** | Shift risk to third party                                                       | "insurance", "outsourcing", "3rd party" | Buy cyber insurance |
| **Accept**   | Do nothing, acknowledge risk                                                    | "business decision", "do nothing", "document acceptance" | Small risk cheaper to accept |
| **Avoid**    | Eliminate activity causing risk                                                 | "discontinue", "remove exposure", "do not perform" | Don’t host in hurricane zone |

---

## Risk Assessment Types

| Term         | Definition / Use                                              | Exam Keywords / Indicators | Scenario |
|--------------|---------------------------------------------------------------|----------------------------|----------|
| **Ad hoc**   | Informal, one-time, triggered by event                        | "after incident", "informal", "specific event" | Quick check after new malware |
| **Recurring**| Scheduled periodically                                        | "quarterly", "annual", "periodic review" | Yearly risk assessment |
| **One-time** | Formal, single assessment (management request)                | "management request", "formal one-off" | Before M&A deal |
| **Continuous**| Automated, ongoing                                           | "automated scanning", "real-time monitoring" | Continuous vulnerability scans |

---

## Quantitative Risk Terms

| Term  | Definition / Formula                                                 | Exam Keywords / Indicators | Scenario |
|-------|----------------------------------------------------------------------|----------------------------|----------|
| **EF (Exposure Factor)** | % of asset value lost in event                     | "% loss", "percentage damage" | Fire causes 40% damage |
| **SLE (Single Loss Expectancy)** | Expected loss for **one incident** <br> SLE = AV × EF | "single occurrence", "one incident" | $100k asset, 30% EF → $30k loss |
| **ARO (Annualized Rate of Occurrence)** | Expected frequency/year | "per year", "once every 5 yrs (0.2)" | Earthquake once in 10 yrs → 0.1 |
| **ALE (Annualized Loss Expectancy)** | Yearly expected loss <br> ALE = SLE × ARO | "annual cost", "expected yearly loss" | $30k SLE × 0.5 ARO = $15k/year |

---

## Risk Register Concepts

| Term             | Definition / Use                                          | Exam Keywords / Indicators | Scenario |
|------------------|-----------------------------------------------------------|----------------------------|----------|
| **KRI (Key Risk Indicator)** | Metric showing change in risk level            | "early warning", "measurable signal" | Increase in failed logins |
| **Risk Owner**   | Person accountable for specific risk                      | "assigned responsibility", "accountability" | IT manager owns phishing risk |
| **Risk Threshold** | Point at which action must be taken                      | "trigger point", "when tolerance exceeded" | Risk score > 8 requires action |

---

## Risk Appetite vs. Risk Tolerance

| Term              | Definition / Use                                          | Exam Keywords / Indicators | Scenario |
|-------------------|-----------------------------------------------------------|----------------------------|----------|
| **Risk Appetite** | How much risk the org is **willing** to take              | "willing to accept", "strategic level" | Startup takes high risk in new tech |
| **Risk Tolerance**| Org’s **ability** to absorb losses                        | "capacity", "financial cushion", "stability" | Large bank can handle more risk due to cash reserves |

---

## Business Impact Analysis (BIA) Terms

| Term  | Definition / Use                                                     | Exam Keywords / Indicators | Scenario |
|-------|----------------------------------------------------------------------|----------------------------|----------|
| **RPO (Recovery Point Objective)** | Max acceptable **data loss** (time)     | "last backup", "data age", "acceptable data loss" | Backups every 6 hrs → 6 hr RPO |
| **RTO (Recovery Time Objective)**  | Max time system can be **down**         | "acceptable downtime", "restore within X hrs" | Must restore within 4 hrs |
| **MTBF (Mean Time Between Failures)** | Average **operational uptime** before failure | "reliability", "expected life" | Hard drive lasts 5 yrs |
| **MTTR (Mean Time to Repair)** | Avg time to fix/restore after failure      | "repair time", "restore service" | Replace failed router in 2 hrs |

---

# ✅ Quick Exam Tips

- If question mentions **installing, patching, reducing risk** → **Mitigate**  
- If **insurance, outsourcing, contracts** → **Transfer**  
- If **document and accept, low risk** → **Accept**  
- If **don’t do activity at all** → **Avoid**  

- **Ad hoc** = after specific event  
- **Recurring** = scheduled (quarterly/annual)  
- **Continuous** = automated scanning  

- **SLE = AV × EF**  
- **ALE = SLE × ARO**  

- **RPO = data loss tolerance**  
- **RTO = downtime tolerance**  
- **MTBF = reliability**  
- **MTTR = repair speed**


# Domain 5.3 – Key Terms & Exam Indicators

## Vendor Assessment Methods

| Term | Definition | Scenario/Indicator (Exam) | Keywords/Triggers |
|------|-------------|---------------------------|-------------------|
| **Pentest** | Simulated cyberattack against vendor system | You need to verify vendor security from the **outside attacker’s view** | "Simulate attack", "test security posture" |
| **Right-to-Audit Clause** | Contract clause allowing you to audit vendor’s practices | Included in contracts for oversight | "Contract clause", "audit vendor" |
| **Evidence of Internal Audits** | Vendor provides proof they audit themselves | You ask vendor for logs/reports | "Proof of audits", "internal security checks" |
| **Independent Assessments** | External auditor reviews vendor | CSP or vendor provides **SOC 2 / ISO 27001** | "External audit", "third-party report" |
| **Supply Chain Analysis** | Check security of **vendors + subcontractors** | Risks may come from 3rd-party suppliers | "Subcontractor", "ecosystem", "vendor chain" |

---

## Right-to-Audit (Detailed)

- Customers may **audit vendors** via **contract clauses**.  
- **BUT**: You cannot audit **public CSPs** (AWS, Azure, GCP). Instead → use **independent attestation reports**.  

**Exam keywords**:  
- "Right-to-audit clause" = **private vendors**.  
- "Cloud vendor" = **look for SOC 2 / ISO 27001**.  

---

## Supply Chain Analysis – Exam Indicators

| Method | Definition | Exam Trigger |
|--------|-------------|--------------|
| **On-Site Assessment** | Visit vendor, interview staff | "Visit facility", "observe processes" |
| **Document Exchange & Review** | Review policies/docs | "Review vendor policies", "doc exchange" |
| **Policy Review** | Request official security procedures | "Review security policies" |
| **Third-Party Audit** | External audit firm provides report | "Independent verification", "SOC 2 / ISO" |

---

## Vendor Selection

### Due Diligence (Easy Analogy)
- **Why is it called this?** → "Due" = what you **must** do. "Diligence" = careful research.  
- **Definition**: Research/checks you do **before signing contract**.  
- **Scenario**: Before hiring vendor, you check their **financials, reputation, compliance, security**.  
- **Exam keyword**: "Before signing", "review vendor financial health", "vendor viability".  

### Due Care
- **Actions taken** after due diligence.  
- Example: If due diligence shows weak security → due care = adding contract clauses or rejecting them.  

---

### Conflicts of Interest
- **Financial**: Employee has stake in vendor (biased decision).  
- **Bribes/Kickbacks**: Inflated contracts, relaxed quality standards.  
- **Professional**: Pre-existing personal ties or "revolving door" employment.  

**Exam keywords**:  
- "Employee’s brother owns vendor" → **Conflict of Interest**.  
- "Former employee joins vendor" → **Revolving door**.  

---

## Agreement Types

| Agreement | Definition | Exam Scenario/Indicator | Keywords |
|-----------|-------------|-------------------------|----------|
| **SLA (Service-Level Agreement)** | Contract defining uptime/downtime, penalties | Vendor promises uptime or response times | "Downtime", "penalties", "performance expectations" |
| **MOU (Memorandum of Understanding)** | Non-binding formal agreement | Two parties intend to cooperate but not legally bound | "Intent", "not legally enforceable" |
| **MOA (Memorandum of Agreement)** | Binding contract (legal) | Legal obligations, enforceable | "Legal agreement", "binding contract" |
| **MSA (Master Service Agreement)** | Governs overall, ongoing vendor relationship | Used with vendors you’ll work with repeatedly | "Ongoing", "general terms", "before SOW" |
| **SOW (Statement of Work)** | Specific deliverables/project agreement | Defines tasks, timelines, deliverables | "Specific project", "after MSA" |
| **NDA (Non-Disclosure Agreement)** | Protects confidential info | Vendor/employee must not share secrets | "Confidentiality", "trade secrets" |
| **BPA (Business Partnership Agreement)** | Partnership for profit between entities | Business venture partnerships | "Profit-sharing", "partnership" |

---

# ✨ Big Picture (Exam Tips)
- **Due diligence** → before contract (research).  
- **Due care** → after contract (actions).  
- **Right-to-audit** → vendors, **not CSPs**.  
- **Supply chain** → always think of **subcontractor risk**.  
- Agreement type questions are often **keyword traps**:  
  - SLA = uptime/downtime  
  - MOU = informal, not binding  
  - MOA = binding  
  - MSA = ongoing  
  - SOW = specific project  
  - NDA = confidentiality  
  - BPA = partnership/profit



  # Consequences of Non-Compliance (Domain 5.4)

| Consequence         | Explanation                                                                 | Exam Keywords / Scenario                                                                 |
|---------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **Fines**           | Monetary penalties imposed by regulators for non-compliance.                | “Financial penalty,” “monetary punishment,” GDPR (up to 4% global revenue), PCI fines.   |
| **Sanctions**       | Legal enforcement → civil or criminal charges.                             | “Criminal liability,” “government action,” mishandling classified data, export violations.|
| **Reputational Damage** | Loss of trust from customers, partners, investors; long-lasting impact.     | “Loss of customer trust,” “brand value harmed,” major data breach disclosure.            |
| **Loss of License** | Revocation of authority to operate in industry or handle certain data.      | “Authorization removed,” “regulator shut down,” HIPAA/financial license revoked.         |
| **Contractual Impacts** | Business agreement penalties → fines, SLA breaches, contract termination.   | “Breach of contract,” “SLA penalties,” “partnership termination,” NDA violations.        |


  
