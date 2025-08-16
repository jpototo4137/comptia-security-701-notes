# Domain 4.1 – Apply Common Security Techniques to Computing Resources

---

## Controls, Benchmarks, Baselines
- **Control** → High-level description, not specific to a technology  
- **Benchmark** → Security recommendations  
- **Baseline** → **Implementation** of the benchmark (actual applied config)  

**Cheatsheet – Control vs Benchmark vs Baseline**

| **Term**    | **Meaning** | **Exam Note** |
|-------------|-------------|----------------|
| **Control** | General, high-level description of security | Not tied to tech |
| **Benchmark** | Standardized recommendation | Reference point |
| **Baseline** | Implementation of benchmark | What’s actually configured |

---

## Security Baselines
- **Establish**: critical for consistency, benchmarking, tailoring to org needs  
- **Deploy**:  
  - Automation/tools (**IaC, Terraform**)  
  - Compliance verification (**SIEM**)  
  - Documentation/change mgmt (**Configuration Mgmt**)  
- **Maintain**:  
  - Continuous improvement  
  - Monitoring/reporting (**SIEM**)  
  - Training/awareness (**STIGs**)  

---

## Hardening Targets

**Definition** → Reduce a system's attack surface / enhancement  

### Mobile Devices
- Updates  
- Segmentation protects data  
- **MDM** → monitor devices, push updates  
- **Exam tip**: Geofencing = prevents devices from leaving premises  

### Workstations
- Desktop/laptop OS (Linux, macOS, Windows)  
- Remove unnecessary software  

### Network Infrastructure Devices
- **Switch**:  
  - Secure access controls  
  - VLAN segmentation  
  - Disable unused ports/services  
- **Router**:  
  - Strong encryption  
  - ACLs  
  - Regular firmware updates  
- Authentication must be changed from defaults  

### Cloud Infrastructure (DevOps, CI/CD, IaC)
- **Least privilege**  
- **IAM** (Identity and Access Mgmt)  
- **EDR** (endpoint detection/response) → all devices accessing cloud must be secure  
- **C2C backups** (cloud-to-cloud)  

### Servers
- Default config not safe  
- Updates  
- User accounts → enforce min pw length/complexity + account limitations  
- Limit network access  
- Antivirus/antimalware  

### ICS/SCADA
- **ICS** → large industrial control systems (energy, logistics, refining, manufacturing)  
- Network segmentation → isolate ICS/SCADA from corporate  
- Often use **air gap** for isolation  
- **PC manages equipment**, benefits from distributed control: real-time info, system control  

### Embedded Systems
- Limited security  
- Patch/firmware updates  
- Firmware integrity checks  
- Place in segmented networks with firewalls  

### RTOS (Real-Time OS)
- Deterministic processing schedule (industrial, military, automobiles)  
- **Hardening**:  
  - Real-time monitoring  
  - Resource access control  
  - Timely patch mgmt  
  - Isolation from other systems  
  - Minimal services  
  - Host-based firewall for secure comms  

### IoT Devices
- Examples: heating/cooling, lighting, wearables  
- Weak defaults  
- **Hardening**:  
  - Update firmware quickly  
  - Change default passwords  
  - VLAN segmentation  

**Cheatsheet – Hardening Targets**

| **Target** | **Key Hardening Focus** | **Exam Keyword/Trap** |
|------------|--------------------------|-----------------------|
| Mobile     | Updates, **MDM**, segmentation | **Geofencing** |
| Workstation | Remove unnecessary software | OS-specific configs |
| Switch     | ACLs, VLAN, disable ports | Physical access risk |
| Router     | Encryption, ACLs, firmware | Default creds trap |
| Cloud      | Least privilege, **IAM**, EDR | C2C backups |
| Servers    | Updates, pw policies, AV | Default config unsafe |
| ICS/SCADA  | Segmentation, **air gap** | Critical infra |
| Embedded   | Patch, firmware integrity | Segmentation |
| RTOS       | Minimal services, firewall | Deterministic ops |
| IoT        | Updates, VLANs, pw change | Weak defaults |

---

## Wireless Devices

### Site Surveys
- Wireless landscape analysis  
- Identify APs, frequencies  
- Heat maps → signal strengths  
- Ongoing surveys needed  

### Wireless Survey Tools
- Coverage, interference checks  
- Built-in or 3rd-party tools  
- Spectrum analyzer  

### Installation Considerations
- Placement, power levels, overlap  

---

## Mobile Solutions

### Mobile Device Management (MDM) - policy
- Centralized mgmt of org/personal devices  
- Set policies on apps, data, camera  
- Control remote devices  
- Partition for business use  
- Access control (pins)  

**Deployment Models**
- **BYOD** → hard to secure  
- **COPE** (Corporate owned, personally enabled) → org owns device, user can use personally  
- **CYOD** (Choose your own device) → org lets users pick device, but applies policies  

### Cellular Networks (4G/5G)
- Security concerns: traffic monitoring, location tracking, worldwide access  

### Wi-Fi
- Security concerns:  
  - Data capture  
  - On-path attacks  
  - DoS (frequency interference)  
- Encrypt when using public Wi-Fi  

### Bluetooth
- Short-range PAN  
- Risks: unauthorized connections, malicious pairing  

**Cheatsheet – Mobile & Wireless**

| **Tech** | **Risk/Focus** | **Exam Keyword/Trap** |
|----------|----------------|-----------------------|
| **MDM**  | Central mgmt, enforce **policies** | BYOD vs COPE vs CYOD |
| **BYOD** | User device → insecure | Hardest to secure |
| **COPE** | Org-owned + personal use | Org has full control |
| **CYOD** | User chooses device | Still under org control |
| **Cellular** | Tracking, monitoring | Global access risk |
| **Wi-Fi** | Encryption, sniffing | Public Wi-Fi danger |
| **Bluetooth** | Unauthorized pairing | PAN exploitation |

---

## Wireless Security Settings
- Users must **authenticate** (username/pw/MFA)  
- Use **MIC** (Message Integrity Check)  
- Network segmentation (VLANs)  

### WPA3
- Replaces WPA2 (brute force vulnerability)  
- **GCMP cipher** (AES + GMAC)  
- **SAE (Simultaneous Auth of Equals)** → dragonfly handshake  
- No 4-way handshake → resistant to brute-force/dictionary  

### Wireless Security Modes
- **WPA-Personal (PSK)** → shared key  
- **WPA3-Enterprise (802.1X)** → per-user auth via RADIUS  

### AAA Framework
- Identification → Authentication → Authorization → Accounting  

### Protocols
- **RADIUS** → centralized AAA (VPN, 802.1X, servers)  
- **IEEE 802.1X (NAC)** → port-based access control (wired/wireless)  
- **EAP** → suite of auth methods (works with 802.1X)  

**Cheatsheet – Wireless Security**

| **Protocol** | **Purpose** | **Exam Keyword/Trap** |
|--------------|-------------|-----------------------|
| **WPA2**     | Legacy, vulnerable | Brute-force risk |
| **WPA3**     | SAE, GCMP | Strongest wireless security |
| **PSK**      | Shared password | Same key for all |
| **Enterprise** | Per-user RADIUS/802.1X | Stronger auth |
| **AAA**      | Identify → Auth → Authorize → Account | RADIUS, TACACS+ |
| **802.1X**   | NAC, port-based | Used with RADIUS/EAP |
| **EAP**      | Extensible auth | EAP-TLS common |


**Comparison: 802.1X vs RADIUS vs EAP vs NAC vs WPA3**

**Overview**

- **802.1X** → handles port-based authentication (often uses EAP + RADIUS)  
- **RADIUS** → provides AAA (authentication, authorization, accounting), supports VPN/Wi-Fi  
- **EAP** → framework for wireless authentication (EAP-TLS, PEAP, etc.)  
- **NAC** → checks device posture/security, can integrate with 802.1X  
- **WPA3** → modern Wi-Fi encryption standard (replaces WPA2)  

---

## Detailed Comparison

| **Term** | **What it is** | **When to Choose (Exam Keyword / Scenario)** |
|----------|----------------|----------------------------------------------|
| **802.1X** | IEEE **port-based authentication standard**. Controls access to LAN/WLAN at the switch or AP level. | **Keyword:** “port-based authentication”, “controls access before network connection”. <br>Example: Preventing rogue devices from joining Wi-Fi/LAN. |
| **RADIUS** | Authentication server/protocol. Centralizes **AAA** (Authentication, Authorization, Accounting). Often backs **802.1X**. | **Keyword:** “centralized authentication”, “remote access”, “VPN or Wi-Fi auth server”. |
| **EAP** | Framework for many wireless authentication methods (EAP-TLS, PEAP, etc.). Works **inside 802.1X**. | **Keyword:** “wireless authentication method”, “certificate-based login”, “WPA2/WPA3-Enterprise”. |
| **NAC** | Enforces security posture **before granting network access** (check patch level, AV, compliance). Can use 802.1X. | **Keyword:** “health check before network access”, “only compliant devices allowed”. |
| **WPA3** | Wi-Fi security standard. Improves WPA2 (stronger encryption, SAE handshake). | **Keyword:** “Wi-Fi encryption”, “latest wireless security”, “replace WPA2”. |

---

How They Relate

- **802.1X** = the standard (door guard)
- **EAP** = the method of proving identity (ID card)
- **RADIUS** = the server that validates the ID (security desk)
- **NAC** = checks if you’re healthy & compliant before entry (health screening)  
- **WPA3** = ensures your wireless traffic is safe once you’re inside (encrypted hallway)

---

## Application Security

### Secure Coding Concepts
- **Input validation** → sanitize forms, prevent injection  
- **Secure cookies** → HTTPS only, no sensitive data  
- **Static code analyzers (SAST)** → catch flaws (buffer overflow, injection); false positives possible  
- **Code signing** → asymmetric crypto: CA signs dev’s public key, dev signs code w/ private key  

### Sandboxing
- App isolation → prevents cross-resource access  
- Safe testing environment  

### App Security Monitoring
- Real-time logs  
- Detect blocked attacks (SQL injection attempts)  
- Audit logs, anomaly detection  

**Cheatsheet – App Security**

| **Concept** | **Purpose** | **Exam Keyword/Trap** |
|-------------|-------------|-----------------------|
| Input Validation | Sanitize inputs | Prevent SQLi/XSS |
| Secure Cookies | HTTPS only | No sensitive data |
| SAST | Static analysis | False positives |
| Code Signing | Auth + integrity | Private key = sign |
| Sandboxing | Isolate apps | Safe testing |
| Monitoring | Logs + anomaly detection | Detect attacks |

---

**Code Signing vs Input Validation vs SAST**

Overview

- **Code Signing** → Ensures code integrity & authenticity using **digital signatures**.  
- **Input Validation** → Prevents malicious/invalid inputs from exploiting the app.  
- **SAST (Static Application Security Testing)** → Analyzes **source code** for vulnerabilities before execution.  

---

**Detailed Comparison**

| **Concept** | **What it is** | **Mitigates / Counters** | **When to Use / Exam Keywords** |
|-------------|----------------|---------------------------|----------------------------------|
| **Code Signing** | Uses **digital signatures** to verify code comes from a trusted source and was not tampered with. | Counteracts **malware-injected software**, **tampered apps**, and **supply chain attacks**. | **Keyword:** “software authenticity”, “trusted vendor”, “prevent tampering”. <br>Example: Ensuring an app downloaded hasn’t been altered with malicious code. |
| **Input Validation** | Validates & sanitizes **user inputs** before processing to block injection attacks, XSS, buffer overflows. | Mitigates **SQL injection**, **cross-site scripting (XSS)**, **buffer overflow**, and **command injection**. | **Keyword:** “prevent malformed input”, “sanitize user input”, “defend against SQL injection/XSS”. |
| **SAST** | **Static code analysis** — scans **source code** or binaries without executing them, to find vulnerabilities early in the SDLC. | Counters **logic flaws**, **hardcoded credentials**, **unsafe functions**, and **potential injection points**. | **Keyword:** “analyze source code”, “before runtime”, “developer IDE or CI/CD pipeline”. |

---

How They Relate

- **Code Signing** = Trust the *origin* of code (is it from who it says it’s from?).  
- **Input Validation** = Protect the *execution* of the app from bad/malicious inputs.  
- **SAST** = Detect flaws *inside the code itself* before it runs.  

---

Exam Tip

- If the question mentions **trusted software vendor / tampering prevention** → **Code Signing**  
- If it mentions **SQL injection, XSS, malformed data** → **Input Validation**  
- If it mentions **static analysis, before runtime, scanning source code** → **SAST**  

---

# Domain 4.2 – Asset Management

## Acquisition / Procurement Process
**Key activities**  
- Check for **valid licenses** (avoid pirated software).  
- Verify **no major vendor security incidents**.  
- Install **secure OS with latest patches**.  

**Security concerns**  
- Malware-infected hardware from **untrusted vendor**.  

**Cheatsheet – Acquisition**

| **Activity** | **Why it matters** | **Security concern** |
|--------------|--------------------|-----------------------|
| Valid licenses | Avoid pirated software | Malware, legal risk |
| Vendor check  | Trusted sources only | Vendor compromise |
| Secure OS     | Patch vulnerabilities | Zero-day exposure |

---

## Assignment / Accounting
**Key activities**  
- Define **ownership** → who is responsible (person, dept, team).  
- Apply **classification** (confidential vs public).  

**Importance**  
- Ensures appropriate **access controls**.  

**Security concerns**  
- Unauthorized access → **data breaches**.  

**Cheatsheet – Assignment**

| **Activity** | **Why it matters** | **Security concern** |
|--------------|--------------------|-----------------------|
| Ownership    | Accountability | Orphan assets |
| Classification | Correct access controls | Overexposure |
| Accounting   | Track responsible party | Insider misuse |

---

## Monitoring / Asset Tracking
**Key activities**  
- Maintain **inventory** of assets.  
  - Track in **CMDB** (Configuration Management Database).  
- **Enumeration** → identify/document all assets on the network.  

**Importance**  
- Tracking = faster **incident response**.  

**Security concerns**  
- **Unknown/untracked assets** = blind spots, higher breach risk.  

**Tracking physical assets**  
- Maintain up-to-date **asset register** (periodic audits, e.g. annually).  
- **Tagging & recording** → barcodes/QR codes.  

**Cheatsheet – Monitoring**

| **Activity** | **Why it matters** | **Security concern** |
|--------------|--------------------|-----------------------|
| Inventory (CMDB) | Visibility of all assets | Missed assets |
| Enumeration | Network discovery | Blind spots |
| Physical tagging | Track hardware | Theft, shadow IT |

---

## Disposal / Decommissioning
**Key activities**  
- **Sanitization** → securely erase storage.  
- **Destruction** → destroy assets beyond recovery.  
- **Certification** → proof of secure disposal.  
- **Data retention** → define how long data is kept.  

**Importance**  
- Improper disposal → **data leaks** / privacy violations.  
- Deleted data must not be recoverable (even with forensics).  
- Retention policies = compliance + reduced risk.  
- **Keeping data longer than needed increases risk**.  

**Security concerns**  
- Residual data on disposed assets (e.g. incomplete wipes).  
- Failure to follow **retention policies** (e.g. storing customer data too long).  

**Cheatsheet – Disposal**

| **Activity** | **Why it matters** | **Security concern** |
|--------------|--------------------|-----------------------|
| Sanitization | Remove data safely | Residual data |
| Destruction  | Ensure unrecoverable | Data leaks |
| Certification | Proof of secure disposal | Audit gaps |
| Data retention | Compliance, limit risk | Over-retention |

---

# Exam Triggers Quick Recall – Asset Management (4.2)

- **Acquisition** → vendor trust, licenses, patched OS.  
- **Assignment** → ownership + classification → access controls.  
- **Monitoring** → CMDB, enumeration, blind spots if missing.  
- **Physical assets** → tagging, asset register, audits.  
- **Disposal** → sanitization, destruction, certification, retention policy.  
- **Exam traps**:  
  - “Residual data” = incomplete sanitization.  
  - “Data kept longer than necessary” = retention failure.  
  - “Unknown devices on network” = poor enumeration/CMDB.  
  - “No one accountable for asset” = missing ownership/accounting.  
