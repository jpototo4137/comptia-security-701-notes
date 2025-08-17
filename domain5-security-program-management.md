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
