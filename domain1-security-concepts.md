Domain 1 Notes (Security+ SY0-701)

⸻

1.1 - Security Concepts

CIA Triad: Confidentiality, Integrity, Availability
AAA:
	•	Authentication: Provides identity
	•	Authorization: Grants access to resources
	•	Accounting: Logs and audits activity

Non-repudiation: The user cannot deny doing something due to proof (e.g., digital signature)
	•	Proof of origin
	•	Accountability
	•	Often used in emails, transactions, secure logs

⸻

Security Control Categories & Functional Types (Cheatsheet)

Keywords matter, but context matters more — types can overlap.

Categories:
	•	Managerial: Policies & procedures — planning & assessment methods
	•	Technical: Hardware/software — tech controls
	•	Operational: People-driven daily operations (new in SY0-701)
	•	Physical: Tangible, facility/real-world objects

Functional Types:
	•	Deterrent: Discourage violations (e.g., warning signs)
	•	Preventive: Stop violations (e.g., access control, encryption)
	•	Directive: Define acceptable behavior (e.g., policy, guidelines)
	•	Detective: Identify incidents (e.g., audit logs, alerts)
	•	Corrective: Restore systems (e.g., patching, restore)
	•	Compensating: Provide alternative controls (e.g., redundancy)

⸻

1.2 - Authorization Models & Zero Trust

Gap Analysis: Find control deficiencies vs. required standards.
	•	Prepares for external audits (every few years)
	•	Differences → Control Gaps → Audit Report

Zero Trust Network Architecture
	•	Control Plane: Makes access decisions (policy engine/admin)
	•	Data Plane: Executes access and enforces policy (PEP)
	•	Components:
	•	Adaptive identity
	•	Policy-driven access
	•	Policy enforcement: e.g., Azure AD (Entra ID)
	•	Implicit trust zone elimination

⸻

Physical Security / Deception Techniques

Honeypot Method:
	•	Decoy system to attract attackers and observe behavior
	•	Doesn’t affect production systems

Terms:
	•	Honeypot: Single fake system/service
	•	Honeynet: Network of honeypots
	•	Honeyfile: Decoy file (e.g., /docs/salaries.xlsx)
	•	Honeytoken: Fake credentials or data to trigger alerts

⸻

1.3 - Change Management

Change Management Policy: Procedure for making changes to production systems.
	•	Reviewed, tested, approved

Change Control: The process of evaluating change requests (sent to CAB).

Standard Operating Procedures:
	•	Approval process
	•	Ownership
	•	Stakeholder & impact analysis
	•	Test results
	•	Backout plan
	•	Maintenance window

Technical Considerations:
	•	Allow/deny lists, legacy dependencies
	•	Downtime & service/application restarts

Documentation: Maintains change records

Version Control:
	•	Track dev/test/prod code versions (e.g., Git)
	•	Detects conflicts

⸻

1.4 - Cryptographic Solutions

Encryption:
	•	Converts plaintext into ciphertext using an algorithm + key

Levels:
	•	FDE: Full Disk Encryption — entire drive (BitLocker)
	•	Volume/File: Targeted encryption (e.g., sensitive folders)
	•	Transport/Communication: TLS, VPNs

Symmetric Encryption:
	•	One shared secret key (encrypt/decrypt)
	•	Efficient, fast (AES preferred)
	•	Key exchange risk

Asymmetric Encryption:
	•	Public/private key pair
	•	Secure exchange, digital signatures
	•	RSA, ECC

Hybrid: Use asymmetric to exchange symmetric key

Diffie-Hellman / ECC:
	•	Used for shared key generation

Algorithms Summary:
	•	AES: Symmetric, strong
	•	RSA: Asymmetric, digital signatures, SSL/TLS
	•	3DES/RC4: Deprecated/insecure

Digital Signatures:
	•	SHA-256 (hash) + RSA (encrypt hash)
	•	Ensures authenticity, integrity, non-repudiation

⸻

PKI (Public Key Infrastructure)

Concept:
	•	Uses public/private key pairs for secure communication
	•	Validates identity, creates trust via certificates

PKI Components:
	•	CA: Issues certificates
	•	Root CA: Top of chain (self-signed)
	•	Intermediate CA: Issues end certs
	•	RA: Verifies identity
	•	PKI Client: Sends CSR (Certificate Signing Request)
	•	CRL/OCSP: Check revocation status

Chain of Trust:
	•	End cert → Intermediate CA → Root CA

OCSP vs CRL:

Method	Description	Notes
CRL	Periodic revocation list	Slower
OCSP	Real-time status check	Faster

<img width="699" height="781" alt="PKI github" src="https://github.com/user-attachments/assets/5940a110-956e-4e8d-9a7c-24436a43103a" />


Certificate Types:

Type	Use Case
Wildcard	Subdomains (*.example.com)
SAN	Multi-domain cert
Code Signing	App/software integrity
Self-signed	Internal/testing only
Email/User/Machine	Identity validation
EV/OV/DV	Domain and org verification levels


⸻

Cryptographic Tools & Concepts

Hashing:
	•	Converts input to fixed output (e.g., SHA-256)
	•	One-way, used for data integrity

Salting:
	•	Adds randomness before hashing passwords

Key Stretching:
	•	PBKDF2, bcrypt — protect weak passwords

TPM:
	•	Security chip, enables secure boot, used with BitLocker

HSM:
	•	External hardware for key protection in data centers

KMS:
	•	Centralized software for key management (e.g., in cloud)

Secure Enclave:
	•	Isolated chip in device (biometric security)

⸻

Data Protection Techniques

Technique	Function	Use Case
Obfuscation	Hides logic/code	Reverse engineering protection
Steganography	Hides message existence	Covert communication
Tokenization	Replaces sensitive data	PCI DSS compliance
Data Masking	Partially hides data	Customer dashboards/testing

