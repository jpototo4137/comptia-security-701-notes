## Domain 1

---

### 1.1 CIA / AAA / Non-Repudiation

- **CIA Triad**: Confidentiality, Integrity, Availability  
- **AAA**:  
  - Authentication → proves identity  
  - Authorization → grants access  
  - Accounting → logs/audits actions  

**Non-repudiation** means a user **cannot deny** doing something because there’s **proof** (e.g. digital signature)  
✅ Used in emails, transactions, secure logs  
✅ Provides proof of origin & accountability

---

### Security Control Categories & Functional Types

*Keywords but context matters! (can fit into multiple types)*

**Control Categories**  
- **Managerial**: Policies & procedures, planning & assessment  
- **Technical**: Hardware/software controls  
- **Operational** (new in SY0-701): People-driven day-to-day controls  
- **Physical**: Tangible security (locks, CCTV)

**Functional Types**  
- **Deterrent**: discourages (e.g., warning signs)  
- **Preventive**: blocks (e.g., firewalls, encryption)  
- **Directive**: guides (e.g., policies)  
- **Detective**: finds (e.g., audit logs)  
- **Corrective**: restores (e.g., backups)  
- **Compensating**: alternatives (e.g., redundancy)

---

### 1.2 Security Concepts: Authorization Models & Zero Trust

#### Gap Analysis

- Compares current state vs. new regulatory requirements  
- Identifies **control gaps** before audits or compliance reviews

#### Zero Trust Architecture

- "Never trust, always verify"
- Removes implicit trust, uses **continuous validation**

**Control Plane**  
- Policy engine, admin, decision points  
- Adaptive identity, policy-driven control

**Data Plane**  
- Actual access & usage by subject  
- Enforced by **Policy Enforcement Point (PEP)** (e.g. Azure Entra ID)

---

### Physical Security

*(Reference only, to be expanded as needed)*

---

### Deception & Disruption

**Honeypots** = fake systems/services to attract attackers  
- Observe & analyze behavior safely  
- Low risk to real infrastructure

| Type       | Description                                       |
|------------|---------------------------------------------------|
| Honeypot   | Single fake system (e.g. login page)              |
| Honeynet   | Network of honeypots                              |
| Honeyfile  | Single fake file (e.g. hidden spreadsheet)        |
| Honeytoken | Decoy transaction or credential                   |

---

### 1.3 Change Management

**Change Management Program** = Policies for reviewing, testing, and documenting changes  
**Change Control** = The actual process of evaluating and approving a change

**Standard Operating Procedures**
- Approval process
- Ownership
- Stakeholder analysis
- Impact & test results
- Backout plan
- Maintenance window

**Technical Considerations**
- Allow/deny lists
- Downtime & service restart
- Legacy systems (e.g., hybrid cloud)
- Dependencies

**Documentation**
- Record environment states & updates

**Version Control**
- Tracks software/configuration versions (e.g., Git)

---

### 1.4 Cryptographic Solutions & PKI

#### Encryption Types

| Type       | Key Use                | Common Algorithms                |
|------------|------------------------|----------------------------------|
| Symmetric  | Same key for enc/dec   | AES, 3DES, RC4 (legacy)          |
| Asymmetric | Public/private key pair| RSA, ECC                         |

- **Asymmetric**: used for secure web (HTTPS), digital signatures  
- **Symmetric**: efficient for large data, but less secure for key exchange

**Hybrid Approach**  
- Use **asymmetric** to securely exchange a **symmetric** session key  
- Example: HTTPS session negotiation

#### Key Exchange

- **Diffie-Hellman**: creates shared key using asymmetric math  
- **ECC**: shorter key, stronger encryption  

---

#### Certificate Basics & PKI Flow

**PKI = Identity + Encryption + Trust**

1. Browser visits HTTPS site  
2. Site sends digital certificate (X.509)  
3. Browser verifies **chain of trust**  
4. Uses asymmetric → exchange symmetric session key  
5. Rest of communication = symmetric encryption

**Key Components**

| Component        | Role                                           |
|------------------|------------------------------------------------|
| Root CA          | Self-signed, top of trust chain                |
| Intermediate CA  | Issues end-entity certs                        |
| RA               | Verifies identity before certificate issuance  |
| CSR              | Certificate Signing Request sent to RA/CA     |
| CRL / OCSP       | Check if certificate was revoked               |

---

#### Revocation: CRL vs. OCSP

| Method | Description                  | Notes                         |
|--------|------------------------------|-------------------------------|
| CRL    | Certificate Revocation List  | Periodic, larger data         |
| OCSP   | Online status check          | Real-time, faster             |
| Stapling | OCSP response bundled by server | Reduces client-side queries |

---

#### Certificate Types

| Type                  | Use Case                                |
|-----------------------|------------------------------------------|
| Wildcard              | Subdomains (e.g., *.example.com)        |
| SAN                   | Multi-domain                            |
| Code Signing          | Software authenticity                   |
| Self-signed           | Lab/testing                             |
| Email Certificate     | Secure email (S/MIME)                   |
| User/Computer         | Auth in enterprise                      |
| Domain Validation (DV)| Proves control of domain                |
| Org Validation (OV)   | Proves legal/business identity          |
| Extended Validation   | Highest trust, browser bar display      |

---

#### Cryptographic Tools

- **TPM**: motherboard chip for encryption/secure boot  
- **HSM**: secure hardware for key storage (enterprise-level)  
- **KMS**: software for central key management  
- **Secure Enclave**: chip for mobile/biometric data isolation  

---

#### Extra Crypto Concepts

**Hashing**
- One-way, irreversible  
- Used in integrity & digital signature  
- Algorithms: SHA-256 (preferred), MD5 (collision risk)

**Salting**
- Adds randomness to hashes  
- Especially for password storage

**Digital Signatures**
- Uses **RSA** to encrypt SHA-256 hash  
- Verifies origin, integrity, and non-repudiation

**Key Stretching**
- Strengthens weak keys (PBKDF2, bcrypt)

**Blockchain**
- Distributed, tamper-proof ledger  
- Uses consensus to validate transactions

---

### Obfuscation, Steganography & Data Protection

| Technique       | Purpose                                       | Keywords                                   |
|-----------------|-----------------------------------------------|--------------------------------------------|
| Obfuscation     | Scrambles code for reverse engineering defense| Protect source code                        |
| Steganography   | Hides message inside media                    | Covert communication                       |
| Tokenization    | Replace data with non-sensitive token         | Credit cards, secure vault                 |
| Data Masking    | Hide parts of data (****1234)                 | UI display, testing                        |

---
