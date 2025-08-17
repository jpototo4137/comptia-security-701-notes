# 5.1 Summarize elements of effective security governance

## Governance Framework

Effective governance = **policies, standards, guidelines, and procedures** aligned with business objectives and risk management.

- **Policies** → high-level “why and what”  
- **Standards** → specific requirements (measurable)  
- **Guidelines** → best practices / recommendations (optional)  
- **Procedures** → step-by-step “how”  

---

## Policies (High-level direction)

- **Acceptable Use Policy (AUP)**  
  Defines allowed vs. prohibited uses of IT resources (PCs, networks, software, social media).  
  *Ex: downloading unauthorized apps, using corporate email for personal business.*  

- **Information Security Policy**  
  Sets overall direction of security across the org.

- **Supporting Policies:**  
  - **Business Continuity** – keep operations running.  
  - **Disaster Recovery** – restore systems after incident.  
  - **Incident Response** – how to handle security incidents.  
  - **SDLC Policy** – secure software development lifecycle.  
  - **Change Management Policy** – how to manage changes securely.  

---

## Standards (Measurable rules)

- **Password**: NIST & CIS guidance.  
- **Access Control**: ISO 27001 (ISMS).  
- **Physical Security**: access badges, cameras, HVAC, fire suppression.  
  - Standards: ANSI, NFPA, ISO, NIST.  
- **Encryption**: FIPS 140-2/3 mandatory for US federal sensitive data.  

---

## Guidelines (Best practices)

- Recommendations, not mandatory.  
- Help shape procedures but allow flexibility.  

---

## Procedures (How-to steps)

- **Change Management**  
  Ensure security risks are evaluated before changes.  

- **Onboarding/Offboarding**  
  Access control for new hires and terminations.  

- **Playbooks** (SOC)  
  Automated runbooks in SOAR for incident handling.  

### Policies → Procedures Link
- **Policy = Recipe (what & why)**  
- **Procedure = Cooking instructions (how)**  
- Ensures **clarity, consistency, training, and compliance**.  

---

## External Considerations

- **Regulatory** – compliance with industry-specific laws (HIPAA, PCI DSS, GDPR).  
- **Legal** – data breaches, e-discovery requirements.  
- **Industry** – regulated sectors (banking, healthcare, energy).  
- **Local / National / Global** – multi-jurisdiction impact.  

---

## Monitoring & Revision

- **Monitoring** – detect effectiveness & gaps.  
- **Revision** – update policies/procedures as business or threat landscape changes.  

---

## Governance Structures

- **Boards** – highest authority, set direction.  
- **Committees** – specialized focus areas, report to board.  
- **Government Oversight** – NIST, FedRAMP, financial/healthcare regulators.  

- **Centralized model** – one security authority across org.  
- **Decentralized model** – BU-level decisions, with central oversight.  

---

## Roles & Responsibilities (Systems & Data)

- **Data Owner** – senior management, legal rights & accountability.  
  - Cannot delegate ultimate responsibility.  

- **Custodian/Steward** – IT staff, day-to-day handling (CIA triad, logs, backups).  

- **Data Steward (Business)** – ensures meaning/context, applies business rules.  

- **Data Controller** (GDPR) – determines purpose and means of processing.  

- **Data Processor** (GDPR) – processes data on behalf of controller.  

- **Data Subject** (GDPR) – the individual (PII owner)

---

**Data Roles & Responsibilities**

| Role                | Responsibility                                                                 | Exam Keywords / Indicators |
|---------------------|-------------------------------------------------------------------------------|----------------------------|
| **Data Owner**      | - Legal rights & ultimate responsibility for data<br>- Defines classification & access rules<br>- Usually senior management | *Cannot delegate full responsibility*, "legal control", "senior mgmt" |
| **Data Controller** | - Determines why/how data is processed<br>- Ensures compliance (e.g., GDPR)<br>- Responsible party for processing activities | "Determines purpose of processing", "responsible for data" |
| **Data Processor**  | - Processes data **on behalf of controller**<br>- Does not own/control data<br>- Usually vendor/3rd party (cloud provider, payroll service) | "3rd party", "acts on behalf", "processes only as instructed" |
| **Data Custodian**  | - Day-to-day safe custody, storage, transport<br>- Implements technical controls (CIA, backups, logs, permissions)<br>- Often IT staff | *Day-to-day operations*, "technical controls", "storage/backup", "admin staff" |
| **Data Steward**    | - Ensures data quality, accuracy, context<br>- Enforces business rules for data use<br>- Bridges gap between owner and custodian | "Business rules", "data quality", "ensures meaning understood" |
| **Data Subject**    | - The individual whose personal data is collected & processed<br>- Protected by privacy laws (e.g., GDPR, CCPA) | "Person identified by data", "PII", "user/customer" |


## Exam Triggers / Quick Tips
- **Owner vs Custodian**:  
  - *Owner = authority*  
  - *Custodian = implementation*  
  - If question says *"day-to-day"* → **Custodian**  
  - If question says *"senior management"* or *"legal responsibility"* → **Owner**

- **Controller vs Processor (GDPR focus)**:  
  - *Controller = decides purpose*  
  - *Processor = acts on behalf*  

- **Steward vs Custodian**:  
  - *Steward = business rules + meaning*  
  - *Custodian = technical storage + enforcement*  

- **Data Subject**:  
  - If the question mentions *"individual rights, PII, privacy requests"* → **Data Subject**

---

## Exam Tips
- Keywords: *policy = what/why*, *procedure = how*.  
- “Day-to-day” = custodian/steward.  
- Governance = alignment of **business risk, compliance, and security objectives**.  
- Expect questions testing your ability to **map a scenario (policy/procedure violation)** to the correct governance element.

# Domain 5 — 5.2 Risk Management

## Overview
Risk management is the **process of identifying, analyzing, evaluating, and responding to risks** that could affect an organization’s assets and operations.  
It includes **risk identification, assessment, analysis, response, and reporting**.

---

## 1. Risk Identification
Identify threats, vulnerabilities, and assets.

- **Threats**: malicious actors, natural disasters, insider misuse
- **Vulnerabilities**: weak configs, unpatched systems, poor monitoring
- **Assets**: data, systems, infrastructure, reputation

---

## 2. Risk Response Techniques
- **Mitigate** → reduce risk via controls (firewalls, patches, training)
- **Transfer** → insurance, outsourcing to 3rd party
- **Accept** → do nothing, live with risk
- **Avoid** → stop risky activity entirely

---

## 3. Risk Assessment
Broader process of **identifying, analyzing, evaluating, and prioritizing risks**.

### Types of Assessments
- **Ad hoc** → informal, one-time (specific event)
- **Recurring** → periodic (quarterly, annually)
- **One-time (formal)** → after incident / management request
- **Continuous** → automated scans and monitoring

### Risk Assessment vs. Risk Analysis
| Term            | Focus                                  | Activities                                  |
|-----------------|----------------------------------------|---------------------------------------------|
| **Risk Assessment** | Broader process across lifecycle       | Identify → Analyze → Prioritize → Mitigate   |
| **Risk Analysis**   | Detailed examination of specific risks | Evaluate **likelihood** + **impact**        |

---

## 4. Risk Analysis

### Qualitative vs Quantitative
- **Quantitative**: numeric, $$-based, formulas (objective)
- **Qualitative**: low/med/high, scoring systems (subjective)

### Key Formulas (Quantitative Risk Analysis)
- **Exposure Factor (EF)** = % of asset value lost  
  - Example: $30k loss on $100k asset → EF = 30%
- **Single Loss Expectancy (SLE)** = AV × EF  
  - Ex: $100k × 30% = $30k
- **Annualized Rate of Occurrence (ARO)** = how often/year  
  - Ex: once every 5 yrs → ARO = 0.2
- **Annualized Loss Expectancy (ALE)** = SLE × ARO  
  - Ex: $30k × 0.2 = $6k/year loss

---

## 5. Risk Register
Tool to **track risks** and their handling.  

**Typical fields:**
- Risk ID
- Description
- Probability
- Impact
- Severity
- Response
- Owner

### Visual Tools
- **Risk Matrix** → likelihood × impact (green → red)
- **Heat Map** → visual severity

### Key Concepts
- **Key Risk Indicators (KRIs)**: metrics to signal changes
- **Risk Owners**: accountability assigned
- **Risk Threshold**: tolerance limit for risks

---

## 6. Risk Tolerance vs Appetite
- **Tolerance** → ability to absorb risk (financial buffer, resources)
- **Appetite** → willingness to accept risk
- **Alignment is critical**: Startups often have **high appetite**; gov/healthcare have **low appetite**.

---

## 7. Risk Management Strategies
- **Acceptance** → do nothing (Exception = temporary, Exemption = permanent)
- **Mitigation** → apply safeguards, accept residual risk
- **Transference** → insurance, outsourcing
- **Avoidance** → stop risky activity

---

## 8. Risk Reporting
- Final phase: risks reported with **recommendations**
- Leadership decides: which risks to accept, mitigate, or transfer

---

## 9. Business Impact Analysis (BIA)
Identifies **mission-critical functions**, **downtime limits**, and **dependencies**.

### Key Metrics
- **RPO (Recovery Point Objective)** → max tolerable data loss
- **RTO (Recovery Time Objective)** → max downtime before unacceptable impact
- **MTBF (Mean Time Between Failures)** → expected uptime before failure
- **MTTR (Mean Time To Repair)** → how long to fix/restore

### Supporting Concepts
- **CBA (Cost-Benefit Analysis)** → compare safeguard costs vs protection
- **ROI (Return on Investment)** → evaluate effectiveness

---

## 10. Exam Angle
- Expect log interpretation questions: e.g., given SLE, EF, ARO, compute **ALE**  
- BIA questions often test differences between **RTO vs RPO**  
- Watch out for **Exception vs Exemption** trick wording  
- Heat maps and risk registers show up in **scenario-based** questions  

---

# Domain 5.3 – Security Program Management & Oversight

## Vendor Assessment

**Common Methods**
- **Penetration Testing** – simulate cyberattacks to test vendor security.
- **Right-to-Audit Clause** – contract clause allowing audits of vendor practices.
- **Evidence of Internal Audits** – request proof of vendor’s regular audits.
- **Independent Assessments** – review reports from external security firms.
- **Supply Chain Analysis**
  - Map vendor ecosystem (subcontractors, suppliers).
  - Ensure vendors are secure, reliable, trustworthy.
  - Use **periodic attestation** – vendors confirm compliance.

**Strong People & Project Management**
- Assess vendor viability (not just security team):
  - Financial statements
  - Performance history/reputation
  - Formal reports (e.g., SOC 1)

---

### Right-to-Audit
- Defines customer rights to investigate vendor’s practices.
- **Exam tip:** You **cannot audit a CSP** (Microsoft, AWS, Google). Instead, rely on **3rd-party reports (SOC 2, ISO 27001)**.

**Audits may uncover:**
- Inferior quality/faulty goods  
- Short shipments  
- Non-delivery  
- Kickbacks/gifts/bribes  
- Fake or unnecessary services  

---

### Supply Chain Analysis
- **On-Site Assessment** – visit vendor, interview staff.  
- **Document Exchange & Review** – check processes.  
- **Policy Review** – request copies of security docs.  
- **Third-Party Audit** – external, independent check.  

---

## Vendor Selection

### Due Diligence
- Collect/analyze info before contract.
- Check:
  - Financial health
  - Reputation
  - Security practices
  - Regulatory compliance

> **Due diligence** → research phase  
> **Due care** → actions based on that research  

### Conflicts of Interest
- **Financial interests** – ownership stakes, bribes, kickbacks.  
- **Professional relationships** – personal ties or “revolving door” (employee leaves → joins vendor).  

### Information Sharing Risks
- **Confidentiality breaches** – vendor misuses data.  
- **Unequal info sharing** – vendor hides limitations → biased decisions.  

---

## Agreement Types

- **SLA (Service-Level Agreement)**
  - Defines performance expectations (uptime, downtime).
  - Includes penalties if not met.

- **MOU (Memorandum of Understanding)**
  - Formal but non-binding.
  - More formal than handshake, less binding than SLA.

- **MOA (Memorandum of Agreement)**
  - Binding legal contract.
  - Different from MOU → enforceable.

- **MSA (Master Service Agreement)**
  - Governs **overall ongoing relationship**.
  - Covers general terms, breach notifications, duties.
  - Comes **before** SOW.

- **SOW (Statement of Work)**
  - Governs **specific project/deliverable**.
  - Follows MSA.

- **NDA (Non-Disclosure Agreement)**
  - Protects company’s confidential info.  
  - Used with vendors, suppliers, and employees.

- **BPA (Business Partnership Agreement)**
  - Between businesses joining to make a profit.  

**Exam keywords**:  
- SLA → uptime/downtime, penalties  
- MOU → informal agreement, not binding  
- MOA → binding contract  
- MSA → ongoing relationship  
- SOW → specific project work  
- NDA → confidentiality  
- BPA → business venture  

---

## Vendor Monitoring
- Continuous monitoring of vendor security posture.
- Send periodic **questionnaires** to check practices.

### Rules of Engagement
- Define test scope, purpose, and boundaries.
- Clarify expectations and escalation path.
- Ensure all parties agree on processes before monitoring.  

---

# ✨ Exam Big Picture (Why it Matters)
- Vendors and supply chains are common **attack surfaces** (e.g., SolarWinds, Target breach).
- Security teams must ensure **due diligence** (research) + **due care** (actions).
- Contract types (SLA, MSA, SOW, NDA) = **keyword traps on exam**.
- Supply chain questions often test whether you recognize:
  - **You can’t audit CSP directly** → rely on 3rd-party attestation.
  - **Due diligence vs. due care**.
  - **Conflict of interest scenarios** (e.g., employee’s brother owns the vendor).
 

# Domain 5.4 – Effective Security Compliance

---

## Compliance Reporting

- **Internal Reporting**
  - Informing leadership & internal stakeholders
  - Keeps executives aware of risks (they are ultimately accountable)

- **External Reporting**
  - Regulatory bodies / auditors (mandatory per laws/regulations)
  - Examples: **GDPR, PCI-DSS, HIPAA**
  - Reporting may be annual, quarterly, or "on-request"

---

## Consequences of Non-Compliance

- **Fines** – monetary penalties, may escalate to lawsuits  
- **Sanctions** – civil or criminal charges  
- **Reputational Damage** – long-lasting trust loss  
- **Loss of License** – inability to operate legally  
- **Contractual Impacts** – penalties or termination of agreements  

---

## Compliance Monitoring

- **Due Diligence** – assess vendors, systems, data handling practices  
- **Due Care** – implement controls/mitigations to reduce identified risks  
- **Attestation & Acknowledgement** – formal confirmation from employees/vendors that they follow policies  
- **Audits**
  - Internal – proactive, fix issues before external checks  
  - External – regulators or third parties  
- **Automation**
  - SIEM & SOAR for monitoring, reporting, and incident response  
  - Helps standardize compliance evidence  

---

## Privacy vs. Confidentiality

- **Privacy** – individual’s right to control personal information  
- **Confidentiality** – organization’s duty to protect data from unauthorized access  

---

## Privacy Frameworks

- **United States**
  - Fourth Amendment → limits gov’t search  
  - SCA (Stored Communications Act, 1986)  
  - Sector-specific (HIPAA, GLBA, etc.)

- **European Union**
  - **GDPR** – applies to all organizations handling EU citizens’ data  
  - Global impact → affects US companies with EU customers  

---

## Key Legal Concepts

- **Data Subject** – person whose personal data is collected  
- **Controller** – entity determining purpose/means of processing  
- **Processor** – processes data on behalf of controller  
- **Ownership** – ultimate control/authority over data  
- **Data Inventory & Retention**
  - Keep detailed record of personal data  
  - Apply retention policies → securely dispose of data after use  
- **Right to be Forgotten**
  - Individuals can request deletion of personal data  

---

## Business Terms & Exam Indicators

- **Attestation** – signed proof of compliance ("we did this")  
- **Acknowledgement** – acceptance of responsibility ("I will follow policy")  
- **Evidence in Logs** – regulators may require:
  - Access logs (who viewed data, when)  
  - Audit trails (system changes, admin actions)  
  - Retention proof (data securely deleted per policy)  

---

## Exam Tips

- If you see **"proactive check before regulator arrives"** → Internal Audit  
- If you see **"legal/global data protection"** → GDPR  
- If you see **"ownership vs access"** → Privacy = people, Confidentiality = data  
- If you see **"right to be forgotten"** → GDPR, EU context  
- If you see **"continuous monitoring with SIEM"** → Automated compliance evidence  

---

# Domain 5.5 – Types & Purposes of Audits and Assessments

> **Audit vs. Assessment**  
> - Audit = like taking the exam (formal, compliance check).  
> - Assessment = like studying for the exam (informal, improvement-oriented).  

---

## Attestation

**Definition:** Independent verification of compliance, security, or processes.  

### Internal
- Conducted by **internal auditors** (dedicated team).  
- Must be **independent** = free to report results without retaliation.  
- **Compliance Audits:** Ensure adherence to internal policies & procedures.  
- **Audit Committee:** Reports to board of directors; oversees audit functions.  
- **Self-Assessments:** Done by staff → identify weaknesses before external checks.  

### External
- Conducted by **external auditors** (3rd-party).  
- **Regulatory Audits:** Required by gov/regulators (e.g., **SOX** for public companies).  
- **Examinations:** Broad reviews (financial, IT, operational).  
- **Independent Third-Party:** Objective review → adds credibility.  

---

## Penetration Testing

**Purpose:** Simulate cyberattacks to evaluate resilience of systems, networks, and people.  

### Categories
- **Physical:** Test physical barriers (locks, guards, entry controls).  
- **Offensive:** Focus on **technical exploitation** (hacking systems).  
- **Defensive:** Assess effectiveness of existing security controls.  
- **Integrated:** Combines physical + offensive + defensive.  

### Types
- **White Box (Known Environment):** Tester has **full info** (e.g., source code, configs).  
- **Black Box (Unknown):** Tester knows **nothing** (true outsider perspective).  
- **Gray Box (Partial):** Tester has **limited info** (like an insider with restricted access).  

**Exam Keywords:**  
- White box = “full visibility”  
- Black box = “blind”  
- Gray box = “limited info”  

### Rules of Engagement
- Defines **scope, purpose, timing, and boundaries** of test.  
- Prevents accidental disruptions.  
- Everyone (security team, vendor, management) must be aware.  

---

## Reconnaissance in Pentesting

### Passive Recon
- **No direct interaction** with target (undetectable).  
- Info gathering from public sources:  
  - WHOIS, DNS records, Google dorking, social media, press releases.  
- Exam keyword: **“target unaware,” “public info.”**

### Active Recon
- **Direct interaction** with target (detectable, may be logged).  
- Tools & methods:  
  - Port scans, ping sweeps, vuln scanners, social engineering.  
- Requires **written, signed contract** (legality!).  
- Exam keyword: **“direct probing,” “can be detected.”**

# Domain 5.6 – Security Awareness Practices

> **Purpose:** Build a security-minded workforce to reduce risks from social engineering, insider threats, and human error.  
> Exam focus = recognizing attack indicators + knowing training/response methods.

---

## Social Engineering

### Principles of Social Engineering Success
- **Authority** → "I’m from IT/CEO approved."  
- **Intimidation** → Threat of negative outcome.  
- **Consensus (Social Proof)** → "Others already did this."  
- **Scarcity** → "Offer expires today."  
- **Familiarity (Liking)** → Pretends to know you.  
- **Trust** → Uses insider knowledge.  
- **Urgency** → "Act now, no time to verify."  

**Exam keyword:** "psychological manipulation"  

---

### Types of Social Engineering

#### Physical
- **Tailgating** → Unauthorized entry by following employee.  
- **Shoulder Surfing** → Stealing creds by looking over shoulder.  
- **Dumpster Diving** → Extracting info from trash.  
- **Elicitation** → Extract info via casual conversation.  

#### Virtual
- **Phishing** → Mass deceptive emails.  
- **Spear Phishing** → Targeted group/individual.  
- **Whaling** → High-level executives.  
- **Vishing** → Phone-based scam.  
- **Smishing** → SMS/text-based phishing.  
- **Hoax** → False warning to trick user.  
- **Watering Hole Attack** → Compromise a site visited by target.  
- **Pharming** → DNS redirection to fake sites.  

**Exam indicators:** suspicious email, urgency, misspellings, unusual source.  

---

### Spam & SPIM
- **Spam:** Junk email → defend with filters.  
- **SPIM:** Spam over instant messaging → avoid public IDs, use cryptic usernames.  

---

### Mitigating Phishing
- **Simulated Campaigns** → Test employees regularly.  
- **Recognition Training** → Red flags = generic greeting, typos, urgency, attachments.  
- **Clear Reporting Procedures** → How to report without compromising.  

---

## Anomalous Behaviour Recognition

### Risky Behaviour
- Downloading from unknown sites.  
- Clicking suspicious links.  
- Sharing passwords.  
- Leaving devices unattended.  

### Unexpected Behaviour
- Sudden spike in failed logins.  
- Accessing sensitive data outside job role.  
- Unusual working hours.  
- Large data transfers to personal devices.  

### Unintentional Behaviour
- Weak/reused passwords.  
- Falling for phishing & entering creds.  
- Leaving sensitive docs uncollected.  
- Oversharing confidential data.  

**Exam angle:** Logs showing "failed logins," "odd hours," "large transfers" → awareness issue.  

---

## User Guidance & Training

- **Policies/Handbooks:** Reporting suspicious messages, phishing guidance.  
- **Situational Awareness:** Stay updated on evolving threats.  
- **Insider Threat Awareness:** Recognize disgruntled coworker risks.  
- **Password Management:** No reuse, encourage password managers.  
- **Removable Media Risks:** Only authorized USBs, encryption required.  
- **OpSec (Operational Security):** Avoid public Wi-Fi, use VPN.  
- **Hybrid/Remote Security:** Secure home Wi-Fi, avoid personal devices for work data.  
- **Social Engineering Training:** Cover "7 principles of SE."  

---

## Reporting & Monitoring

- **Initial Assessment:** Surveys, tests to measure baseline awareness.  
- **Recurring Training:** Regular sessions, updated content.  
- **Continuous Monitoring:** Track employee improvement, address weak areas.  

---

## Training Program Development & Execution

- **Tailored Content:** Match org’s risks & industry.  
- **Varied Methods:** Online modules, in-person, interactive exercises.  
- **Execution:**  
  - Mandatory for all employees.  
  - Hybrid training (onsite + remote).  
  - Promote awareness program across the org.  

---

**Exam Focus:**
- Keywords like "tailgating," "dumpster diving," "urgency in email" → social engineering.  
- Logs showing unusual login times/data exfiltration → awareness/training gap.  
- Answer choices mentioning "training," "policies," "reporting" usually → mitigation.
