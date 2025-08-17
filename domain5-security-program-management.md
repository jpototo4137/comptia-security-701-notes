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

- **Data Subject** (GDPR) – the individual (PII owner).  

---

## Exam Tips
- Keywords: *policy = what/why*, *procedure = how*.  
- “Day-to-day” = custodian/steward.  
- Governance = alignment of **business risk, compliance, and security objectives**.  
- Expect questions testing your ability to **map a scenario (policy/procedure violation)** to the correct governance element.
