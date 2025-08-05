# Domain 2 – Security+ SY0-701 Notes (Polished)

---

## 2.1 Threat Actors and Motivations

### Types of Threat Actors

- **Nation-state**: APTs (Advanced Persistent Threats)
- **Hacktivist**: Ideological/political actors
- **Insider threat**: Employees, contractors, business partners
- **Organized crime**: For financial gain
- **Unskilled attacker**: Script kiddies
- **Shadow IT**: Unapproved internal systems (not always malicious)

### Attributes of Actors

- Internal / External
- Resource availability & funding
- Level of sophistication / capability

### Motivations

- Financial gain 💰
- Espionage 🕵️
- Revenge 😠
- Ethical or ideological belief
- Data exfiltration
- Blackmail
- Service disruption
- Chaos / war

---

## 2.2 Threat Vectors & Attack Surfaces

> **Threat Vector** = method of attack  
> **Attack Surface** = area that can be exploited

### Message-Based
- **Vectors**: Email phishing, smishing, SIM swapping  
- **Surfaces**: Email clients, SMS apps

### File-Based & Image-Based
- **Vectors**: Malware in files or steganography in images  
- **Surfaces**: File downloads, image viewing

### Voice Call & Removable Devices
- **Vectors**: Vishing, infected USBs  
- **Surfaces**: VoIP platforms, USB ports

### Software Vulnerabilities
- Client-based vs agentless flaws
- Default credentials (brute-force risks)
- Unsupported or outdated applications

### Network
- **Vectors**: Insecure wireless/Bluetooth, open service ports  
- **Surfaces**: Misconfigured routers, public networks

### Human/Social Engineering
- Phishing, smishing, vishing
- **Pretexting**: Faking scenarios for access
- **Impersonation / BEC**
- **Watering hole attacks**: Malicious sites
- **Brand impersonation / Typosquatting**

---

## 2.3 Types of Vulnerabilities

> Vulnerability = flaw  
> Threat = possibility  
> Exploit = method/tool  
> Attack = execution

### Application-Level

- **Buffer Overflow**: Poor input validation → memory injection
- **Integer Overflow**: Numbers exceed buffer limit
- **Race Condition**:
  - TOC (Time of Check)
  - TOU (Time of Use)

- **Malicious Updates**: Use signed updates only

### OS-Level

- Default settings, misconfiguration
- Privilege escalation → use UAC/SUDO
- **Zero-day**: Unknown vulnerabilities → use XDR, IDPS

### Web Vulnerabilities

- **SQL Injection**: Unauthorized DB access
- **XSS (Cross-site scripting)**:
  - Targets client
  - Prevent with input validation & WAF

### Hardware

- Firmware attacks → use TPM secure boot
- Legacy/end-of-life risks

### Virtualization

- **VM Escape**: Break out of sandbox
- **Resource Reuse**: Data remanence risk

### Cloud Vulnerabilities (CSA "Egregious 11")

- Misconfiguration
- Data breach
- Account hijacking
- Insecure APIs
- Weak IAM / control plane

### Supply Chain

- Hardware, software, or service providers  
- Mitigation: vendor risk management

### Cryptographic Weaknesses

- Weak encryption or key length
- Key reuse / poor randomness
- Poor key lifecycle (1-year cert lifespan recommended)
- AES-256 for symmetric encryption
- X.509 → 2048-bit key minimum

### Misconfiguration

Prevent with:
- Configuration management tools (IaC)
- CI/CD
- Security audits, change management

### Mobile

- Sideloading
- Third-party app stores
- Rooting/jailbreaking

---

## 2.4 Indicators of Malicious Activity

### Malware

- **Ransomware**: Encrypted files + ransom note
- **Trojan**: Fake legit software
- **Spyware**: Stealth data collection
- **Worm**: Self-replicating network-spreader
- **Bloatware**: Unneeded pre-installed software
- **Keylogger**: Captures keystrokes
- **Virus**: Injects itself into files
- **Logic Bomb**: Triggered by time/event
- **Rootkit**: Hides attacker presence

**Indicators:**

- Account lockout
- High CPU/Memory/Network use
- Blocked content
- Missing logs / out-of-cycle logging
- Resource inaccessibility

### Physical

- Brute force
- RFID cloning
- Environmental sabotage

### Network Attacks

- **DoS/DDoS**: Overwhelm with traffic  
  - *Amplified*: reflection + large response  
  - *Reflected*: spoofed IP → reply goes to victim  
  - *Exam*: Sudden spike in traffic → DDoS

- **DNS Attacks**:  
  - Poisoning: redirect domain to malicious IP  
  - Spoofing: fake DNS replies  
  - Hijacking: changing domain ownership

- **Wi-Fi/Bluetooth**:
  - Evil twin, rogue AP, Bluejacking, Bluesnarfing, Bluebugging

- **MITM / On-Path**: Intercept data between parties
- **Credential Replay**

### Application Attacks

- Injection (SQLi, XSS)
- Buffer overflow
- Privilege escalation
- Directory traversal (`../../../`)
- Session/Request replay

### Cryptographic

- Downgrade
- Collision
- Birthday attack

### Password Attacks

- **Spraying**: 1 password → many accounts
- **Brute force**: all passwords → 1 account

---

## 2.5 Mitigation Techniques

### Segmentation & Isolation

- Divide and isolate network segments

### Access Control & Least Privilege

- Restrict access based on roles
- "Need to know" principle

### Application Allow List

- Block all except approved apps  
  *Prevents accidental malware install*

### Patch Management

- Regular updates, test before deploy

### Encryption

- Use strong algorithms (AES-256, RSA 2048+)

### Monitoring & Logging

- Use SIEM, detect anomalies, alert triggers

### Configuration Enforcement

- Secure baselines, hardening guides

### Decommissioning

- Remove old devices/systems securely

### Hardening Techniques

- Host-based firewalls, HIPS
- Disable unnecessary services
- Change default passwords
- Remove bloatware
