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
