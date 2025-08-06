# Security+ Domain 3: Security Architecture (SY0-701)

---

## 3.1 Compare and Contrast Security Implications of Different Architecture Models

### Architecture & Infrastructure Concepts

#### Cloud Models

**Cloud Service Models (most user control → least):**

- **IaaS (Infrastructure as a Service)**
    - You manage VMs, networks, guest OS security.
    - CSP provides hardware, staff, datacenter.
    - *More control, more setup needed.*

- **PaaS (Platform as a Service)**
    - CSP manages hardware, OS, provisioning.
    - You manage apps.
    - *Less control, easier deployment.*

- **SaaS (Software as a Service)**
    - CSP manages everything except your config/data.
    - *Least control, easiest use.*

**Shared Responsibility Model:**  
Responsibilities split by service model.

**Cloud Deployment Models:**
- **Public:** Provider’s infra, scalable, pay-as-you-go.
- **Private:** Org’s own DC, more control/compliance.
- **Hybrid:** Mix of public/private for flexibility.
- **Community:** Shared among similar orgs.
- **Multi-cloud:** Multiple public providers, more redundancy.

**Third-party Considerations:**
- Risks: data leaks, outages, compliance, 3rd-party integrations.
- Multi-tenancy: Isolation failures risk data leaks.

---

#### Infrastructure as Code (IaC)

- Automate infra with scripts (YAML, JSON, HCL).
- **Tools:** Terraform, Ansible, CloudFormation, Puppet/Chef.
- **Benefits:** Consistency, version control, automation, security-as-code, less human error.
- **Key Properties:**
    - **Declarative:** Define end state.
    - **Idempotent:** Repeated runs = same result.

---

#### Serverless

- Cloud provider manages servers; you deploy code/functions.
- **Platforms:** AWS Lambda, Azure Functions, Google Cloud Functions.
- **Benefits:** No admin, auto-scaling, pay-per-use, fast deploys.
- **Security:** Secure APIs, least privilege IAM, validate inputs.

---

#### Microservices

- App broken into small, independent services (API-connected).
- **Benefits:** Scalability, fault isolation, tech flexibility, fast updates.
- **Security:** Each API secured, encrypted comms, API gateways/service mesh.
- *Often deployed in containers.*

---

#### Network Infrastructure

- **Physical Isolation:** Air gap = no network connection.
- **Logical Segmentation:** VLANs (Layer 2), VPNs, VRF (virtual routers).

##### Software Defined Networking (SDN)

| Feature            | Traditional Networking        | SDN                    |
| ------------------ | ---------------------------- | ---------------------- |
| Control Plane      | Each device                  | Central controller     |
| Management         | Manual                       | Automated              |
| Flexibility        | Hard                         | Easy/dynamic           |
| Policy Enforcement | Static                       | Programmable           |

- Central controller, dynamic management.
- **Risks:** MITM, DoS (secure with TLS).

---

#### On-premises vs. Off-premises

| Feature            | On-Premises      | Off-Premises (Cloud) |
| ------------------ | ---------------- | -------------------- |
| Physical control   | Full             | Limited              |
| Cost               | High upfront     | Usage fee            |
| Maintenance        | You              | Provider             |
| Security risk      | Local threats    | Cloud/remote threats |
| Scalability        | Hard             | Easy                 |

---

#### Centralized vs. Decentralized

| Feature           | Centralized | Decentralized |
| ----------------- | ----------- | ------------- |
| Location          | Single/few  | Many          |
| Cost              | Lower       | Higher        |
| Management        | Easier      | Complex       |
| Outage Impact     | Wide        | Localized     |
| Scalability       | Less        | More          |
| Security          | Easier      | Harder        |

---

#### Containerization

- Containers bundle app + dependencies, share host OS (Docker, Kubernetes).
- **Containers vs VMs:**  
    - Containers: lightweight, portable, share kernel.
    - VMs: own OS, heavier.
- **Security:** Harden images, non-root users, vulnerability scanning, registry access control, isolation (AppArmor/SELinux).

---

#### Virtualization

- **Hypervisor:** Run multiple VMs on one host.
    - **Type 1:** Bare-metal (ESXi, Hyper-V).
    - **Type 2:** Hosted (VirtualBox).
- **Risks:**  
    - VM Escape (VM to host attack).
    - VM Sprawl (unmanaged, unpatched VMs).
- **Mitigation:** Patch, inventory, automation.

---

#### IoT / ICS / RTOS / Embedded

- **IoT:** Smart devices, often low resources/hard to patch.
- **ICS/SCADA:** Industrial systems, usually not internet connected.
- **RTOS:** Real-time OS for critical timing (medical, industrial).
- **Embedded:** Computer inside device (printers, drones, cars), often unpatchable.

---

#### Key Considerations Table

| Factor           | Meaning                  | Best Fit           | Notes                     |
| ---------------- | ------------------------ | ------------------ | ------------------------- |
| Availability     | Can users access it?     | Cloud, on-prem     |                          |
| Resilience       | Handles failure?         | Cloud, decentralized |                         |
| Cost             | Deploy/maintain cost     | Cloud/depends      | Upfront vs ongoing        |
| Responsiveness   | Low-latency?             | Serverless, edge   | Real-time apps            |
| Scalability      | Grow on demand?          | Cloud, containers  |                          |
| Deployment Ease  | How fast to set up?      | Serverless         | On-prem = slow            |
| Risk Transfer    | Shift liability?         | Cloud              | Shared model              |
| Recovery Ease    | Restore speed?           | Cloud, VMs         | Snapshots/backups         |
| Patchability     | Easy to update?          | Trad OS/VMs        | Embedded = hard           |
| Power/Compute    | Needed for workload      | Local/Cloud        | AI, media, big data       |

---

## 3.2 Apply Security Principles to Secure Enterprise Infrastructure

- **Device Placement:** Location impacts risk.
- **Security Zones:** Intranet, Extranet, DMZ.
- **Attack Surface:** Minimize entry points.
- **Failure Modes:**  
    - **Fail-open:** Less secure, allows traffic.
    - **Fail-closed:** More secure, may disrupt.
- **NIPS/NIDS/TAPs:**  
    - Inline (active), Tap (passive).

### Network Appliances

- **Jump Server:** Secure admin access.
- **Proxies:**  
    - Forward: outbound filtering.
    - Reverse: inbound filtering, SSL offload.
- **IDS/IPS:**  
    - IDS: Detect/log.
    - IPS: Detect/block.
    - HIDS/HIPS: Host only.
    - NIDS/NIPS: Network wide.
    - Signature: Known attacks.
    - Behavior: Unknown/anomaly.

- **Load Balancing:**
    - NIC Teaming, NLBs.
    - Active/Active or Active/Passive.
    - Methods: Least used, round robin, affinity.
    - Virtual IPs.

### Port Security & Access

- **Sensors/Collectors:** Monitor data.
- **802.1x:** Port-based access (uses EAP).
- **Wireless Auth:**  
    - LEAP: Deprecated.
    - PEAP/EAP-TLS/EAP-TTLS: Secure, uses certs/TLS.

### Firewall Types

- **Packet Filtering:** L3/L4, basic/fast.
- **App-Level:** L7, app-specific.
- **Circuit-Level:** L5, session checks.
- **Stateful:** L4+, tracks sessions.
- **Deep Packet Inspection:** Scans payload.
- **WAF:** Web app protection (XSS, SQLi).
- **NGFW:** Adds app awareness.
- **UTM:** Combo device.

### Secure Communication / VPN

- **VPN:** Secure tunnels over public internet.
    - Split tunnel: Corp only.
    - Full tunnel: All traffic.
    - Remote access: Host-to-network.
    - Site-to-site: Router-to-router.
- **IPSec:**  
    - **AH:** Auth only, no encryption.
    - **ESP:** Auth + encryption.
    - **Transport:** Encrypts payload.
    - **Tunnel:** Encrypts whole packet.

### SD-WAN & SASE

- **SD-WAN:** Software-based WAN management, dynamic routing, secure with TLS/IPsec/NGFW.
- **SASE:** Cloud-based, merges security & network, includes FWaaS, SWG, IPS, CASB, DLP.

### Effective Control Selection

1. Identify assets/vulns.
2. Impact analysis.
3. Assess threats.
4. Choose controls (Admin, Technical, Physical).

---

## 3.3 Data Protection Concepts & Strategies

### Data Types

- **Regulated:** PII, PHI, financial.
- **Trade Secret:** Formulas, designs.
- **IP:** Patents, trademarks, copyright.
- **Legal:** Contracts, opinions.
- **Financial:** Invoices, accounts.
- **Human-readable:** Text, images.
- **Non-human-readable:** Code, DB files.

### Data Classifications

- **Sensitive:** Needs protection.
- **Confidential:** Internal only.
- **Public:** No restriction.
- **Restricted:** Legally controlled.
- **Private:** PII, PHI.
- **Critical:** Vital ops data.

### Data States

| State     | Where?          | Examples                   |
| --------- | --------------- | -------------------------- |
| At rest   | Disk/storage    | BitLocker, TDE             |
| In transit| Network         | TLS, HTTPS, VPN            |
| In use    | RAM/CPU         | RAM protections, Cred Guard|

### Data Sovereignty & Geolocation

- Subject to local laws where stored.
- Geolocation for policy (lock/wipe if stolen).

### Data Protection Methods

| Goal              | Method         |
| ----------------- | --------------|
| Partial info      | Masking        |
| Replace/tokenize  | Tokenization   |
| Remove IDs        | Anonymization  |
| Track access      | RBAC           |
| Integrity         | Hashing        |
| Encrypt/decrypt   | Encryption     |
| Harder to read    | Obfuscation    |
| Segment/isolate   | Segmentation   |

### Data Lifecycle

`Creation → Classification → Storage → Usage → Archive → Destruction`

*Excess retention = extra risk!*

---

## 3.4 Resilience and Recovery

| Concept      | Definition                            | Focus      |
| ------------ | ------------------------------------- | ---------- |
| Resilience   | Continue ops during incident          | Proactive  |
| Recovery     | Restore normal after incident         | Reactive   |

### High Availability

- **Load Balancing:** Spreads traffic, auto-failover.
- **Clustering:** DB/back-end, logical unit, data replication.

### Recovery Sites

| Type   | Cost   | Speed     | Details                               |
| ------ | ------ | --------- | ------------------------------------- |
| Hot    | High   | Fastest   | Live mirror, up instantly             |
| Warm   | Medium | Moderate  | HW ready, load software/data needed   |
| Cold   | Low    | Slowest   | Space/power only, build from scratch  |

*Sites should be 300+ miles apart.*

### Platform Diversity & Multi-Cloud

- **Platform Diversity:** Mix OS/vendors to reduce single point of failure.
- **Multi-cloud:** Multiple providers, more redundancy, avoids lock-in.

### Continuity of Operations

- Plans for critical functions, backup, DR, alt comms.

### Capacity Planning

- Ensure enough staff, tech, infra for current/future demands.

### Testing & Exercises

| Type             | Description                      |
| ---------------- | --------------------------------|
| Tabletop         | Paper review of IR plan          |
| Failover         | Shutdown primary, test backup    |
| Simulation       | Emulated test, no real risk      |
| Parallel Proc.   | Run backup site parallel         |

### Backup & Recovery

- **Onsite:** Fast, same site risk.
- **Offsite:** Safer (cloud/remote).
- **Frequency:** Matches data change/importance.
- **Encryption:** Protect backups.
- **Snapshots:** Restore to point-in-time.
- **Replication:** Real-time or scheduled.
- **Journaling:** Logs for replay/recovery.

> **Full backup = fastest recovery (exam!)**

### Power Protection

- **UPS:** Short-term power, clean shutdown, surge/spike protection.
- **Generators:** Long-term, full operations for hours/days.

---

## Flashcards / Spaced-Repetition

| Question                                       | Answer                                  |
| ---------------------------------------------- | ---------------------------------------- |
| Resilience vs Recovery                        | Resilience = during; Recovery = after    |
| Full backup provides?                         | Fastest recovery                        |
| Define warm site                              | HW ready, load data, med speed/cost      |
| UPS in security?                              | Short-term power, safe shutdown          |
| Single cloud risk?                            | Vendor lock-in, no redundancy            |
| Platform diversity?                           | Mix OS/vendors, less failure risk        |
| Failover testing?                             | Shutdown main, test backup               |
| Parallel processing?                          | Run DR site in parallel for test         |
| Journaling helps recovery?                    | Replay data changes, restore state       |
| Geographic dispersion?                        | Avoid region-wide disaster impact        |

---
