# 4.6 Identity and Access Management (IAM)

---

## IAM Basics
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Provisioning / Deprovisioning** | Creating/removing user accounts | New hire/termination processes | Q: Admin offboards user, which IAM function? |
| **Permission Assignment** | Limit user’s access | Ensure least privilege | Q: Which IAM principle ensures minimum required rights? |
| **Identity Proofing** | Validating user identity | High-security environments | Q: Before granting remote access, verify user identity – which process? |

---

## Authentication / Authorization
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **SSO (Single Sign-On)** | One login → access multiple resources | Enterprise apps (email, SharePoint, etc.) | Q: User logs in once, gains access to multiple systems. What is this? |
| **Federation** | Share authentication across orgs | Partner companies, “Login with Google” | Q: User logs in with FB credentials on another site – which concept? |

---

## Protocols / Standards
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **LDAP** | Directory access protocol | Querying Active Directory, enterprise networks | Q: Protocol used to access X.500 directory? |
| **SAML** | XML-based auth/authorization standard | SSO in enterprise web apps | Q: Which standard lets users authenticate once and use multiple web apps? |
| **OAuth** | Authorization framework | Third-party API access (what user can do) | Q: Which framework allows app A to access app B’s resources without sharing password? |
| **OpenID Connect** | Authentication layer on top of OAuth | Sign-in with Google / OIDC tokens | Q: Which adds authentication to OAuth? |

---

## Access Control Models

| Model | Description | Analogy | When to Use | Exam Scenario |
|-------|-------------|---------|-------------|---------------|
| **MAC** | Mandatory Access Control: Labels + clearance levels. | Military “Top Secret” clearance. | Gov/military, highly secure data. | “User cannot change perms, system enforces labels.” |
| **DAC** | Discretionary Access Control: Owner decides who gets access. | Windows folder “Right click → Share.” | Most common in OS (Windows, Unix). | “File owner grants or changes permissions.” |
| **RBAC** | Role-Based Access Control: Permissions tied to roles/groups. | HR group auto gets HR docs. | Large orgs, scalability. | “Finance team gets finance system.” |
| **Rule-based** | System-enforced rules (ACLs, firewall-like). | If/else conditions. | Network/firewall style enforcement. | “Access only if time=9AM–5PM.” |
| **ABAC** | Attribute-Based Access Control: Multiple factors (role, IP, time, location). | Cloud fine-grained policy. | Modern cloud & zero trust. | “User must be in HR role, using corp IP, during work hours.” |

---

## Security Principles
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Least Privilege** | Minimum required rights | Everywhere | Q: Which principle states accounts should have only required permissions? |
| **Time-of-Day Restrictions** | Block access by time | Reduce risk after hours | Q: Policy blocks DB access between midnight–6am, what is this? |

---

## Multifactor Authentication (MFA)
| Factor | Example | When to use | Exam scenario |
|--------|---------|-------------|---------------|
| **Something you know** | Password, PIN | Always baseline | User logs in with password |
| **Something you have** | Token, SMS code | Extra login security | Admin uses smart card |
| **Something you are** | Fingerprint, iris | High security | Biometric scan at door |
| **Somewhere you are** | IP, GPS | Geofencing, remote work | Access only allowed in HQ |

---

## Password Concepts
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Best practices** | Complexity, length, expiration | All users | Q: Which improves password security? |
| **Password managers** | Store securely in DB | User convenience | Q: Which allows secure storage of multiple creds? |
| **Passwordless** | Biometrics, security keys | Modern apps, mobile | Q: Face ID login – which method? |

---

## Privileged Access Management (PAM)
| Concept | What it is | When to use | Exam scenario |
|---------|------------|-------------|---------------|
| **Just-in-Time Access** | Temporary admin rights | Admin tasks, reduce attack surface | Q: Admin gets temp rights for 1 hour – which concept? |
| **Password Vaulting** | Store root/admin creds in vault | High-security IT ops | Q: Which stores and controls access to privileged accounts? |
| **Ephemeral Credentials** | Disposable credentials | Cloud access, temp accounts | Q: Admin gets creds valid for one session – which? |


# 🔑 Identity and Access Management (IAM) Big Picture Cheat Sheet

---

## 🚀 IAM (Identity & Access Management)
- **What:** Framework for identities + access.  
- **When to use:** Always, any org with employees/devices/apps.  
- **Why:** Prevents chaos (no “everyone is admin”).  
- **Analogy:** Security badges in a building.  
- **Exam clue:** Provisioning, SSO, account lifecycle → **IAM**.

---

## 🔐 MFA (Multi-Factor Authentication)
- **What:** More than 1 proof of identity (password + code, fingerprint + card).  
- **When to use:** Sensitive accounts (admins, VPN, banking, cloud).  
- **Why:** Stops stolen password attacks.  
- **Analogy:** Apartment key + fingerprint scanner.  
- **Exam clue:** Scenario about “reduce password attacks” → **MFA**.

---

## 👑 PAM (Privileged Access Management)
- **What:** Special handling for **admin/root** accounts.  
- **When to use:** IT staff, cloud admins, privileged users.  
- **Why:** If admin hacked → attacker owns everything.  
- **Features:**  
  - Just-in-Time (temporary rights)  
  - Vaulting (store admin creds, no one sees them)  
  - Ephemeral creds (self-destruct after use)  
- **Analogy:** Master key melts after 1 hr use.  
- **Exam clue:** “Temporary elevated rights / admin account risk” → **PAM**.

---

## 🗂️ Access Control Models
| Model | Description | Analogy | Exam Scenario |
|-------|-------------|---------|---------------|
| **MAC** | Mandatory labels & clearance | Military clearance | “Top Secret file” |
| **DAC** | Owner decides access | Windows folder “Share” | “File owner gives perms” |
| **RBAC** | Based on role/job group | HR group gets HR files | “Finance team access” |
| **Rule-based** | System-enforced rules | Firewall ACLs | “If/else conditions” |
| **ABAC** | Multi-criteria (location, IP, time) | Cloud fine-grained | “Time-based or location-based access” |

---

## 📡 IAM Protocols & Standards

| Protocol/Standard | What it does | Analogy | When/Exam use |
|-------------------|-------------|---------|---------------|
| **LDAP** | Directory protocol for users/groups | Company phonebook | “Query user DB” |
| **SAML** | Web SSO standard (XML) | Passport for web apps | “Enterprise SSO” |
| **OAuth** | Delegated access (authorization) | Giving valet keys | “Grant access without password” |
| **OpenID Connect** | Identity/auth on top of OAuth | “Sign in with Google” | “Auth built on OAuth” |

---

# 📝 TL;DR Exam Strategy
- **IAM** = Whole framework (accounts, lifecycle, SSO).  
- **MFA** = Stop password-only hacks.  
- **PAM** = Protect admin/root accounts.  
- **Access models** = Philosophies (MAC, DAC, RBAC, ABAC).  
- **LDAP/SAML/OAuth/OIDC** = Protocols that *make IAM work in real life*.  
