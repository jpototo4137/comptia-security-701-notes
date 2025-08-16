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

# Exam Triggers Quick Recall Sheet

### Controls, Baselines
- **Control** → high-level policy, not tech-specific  
- **Benchmark** → recommended settings/standards  
- **Baseline** → actual implementation of benchmark  

### Hardening
- **Default config / default passwords** → insecure, must change  
- **Air gap** → ICS/SCADA isolation  
- **Geofencing** → mobile device can’t leave premises  
- **Least privilege / IAM** → cloud or server security  
- **Remove unnecessary software** → workstation hardening  
- **Firmware updates** → embedded, IoT, routers  
- **Minimal services** → RTOS  

### Wireless & Mobile
- **WPA2** → brute-force/dictionary vulnerable  
- **WPA3** → SAE (dragonfly handshake), GCMP cipher, no brute force  
- **PSK** → everyone shares one password  
- **Enterprise (802.1X)** → per-user auth, backed by RADIUS  
- **MIC** → message integrity check (wireless)  
- **BYOD** → hardest to secure  
- **COPE** → org-owned, user can use personally  
- **CYOD** → user chooses, org still controls  
- **MDM** → centralized management  
- **Public Wi-Fi** → sniffing, on-path attack  
- **Bluetooth** → pairing risk, PAN exploitation  

### AAA & Protocols
- **AAA** → Identify → Authenticate → Authorize → Account  
- **RADIUS** → centralized AAA, VPN, 802.1X  
- **802.1X** → NAC, port-based control  
- **EAP** → flexible framework (TLS, TTLS, etc)  

### Application Security
- **Input validation** → prevents SQL injection  
- **Secure cookies** → HTTPS-only, no sensitive info  
- **SAST** → static code analysis, false positives possible  
- **Code signing** → integrity/authentication, asymmetric crypto  
- **Sandboxing** → isolate apps/resources  
- **Monitoring logs** → detect anomalies & attacks  
