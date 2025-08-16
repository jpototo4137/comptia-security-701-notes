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
| Model | What it is | When to use | Strengths/Weakness | Exam scenario |
|-------|------------|-------------|---------------------|---------------|
| **MAC** | Objects labeled with clearance levels | Military, high security | Very strict, least flexible | Q: Which model is based on labels & clearance? |
| **DAC** | Owner decides access | Typical OS (Windows, Linux) | Flexible but weak | Q: File owner grants access – which model? |
| **RBAC** | Access based on roles/groups | Enterprises with defined job roles | Easier to manage | Q: Admin gives access by “HR group” – which model? |
| **Rule-based** | System-enforced rules | Firewalls, ACLs | Automated control | Q: Firewall allowing traffic by rule – which model? |
| **ABAC** | Based on attributes (IP, time, device) | Modern cloud apps | Fine-grained | Q: User only allowed if using corp laptop during work hours – which model? |

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


🔑 Identity & Access Management (IAM)

What it is: The whole system of who you are (identity) and what you can do (access).
	•	When to use: Always, in any org with employees, devices, or apps.
	•	Why: Without IAM, everyone could log in as “admin” → chaos.
	•	Big picture analogy: Like a building with security badges. IAM decides who gets a badge, what doors it opens, and when it expires.
	•	Exam tip: Questions about provisioning accounts, SSO, authentication → always IAM.

⸻

🔐 Multi-Factor Authentication (MFA)

What it is: Using more than one way to prove you are you (password + phone code, fingerprint + smart card, etc.).
	•	When to use: Sensitive accounts (admins, VPN, remote workers, banking, cloud).
	•	Why: Passwords leak. MFA stops attackers even if they stole your password.
	•	Big picture analogy: Like needing both your apartment key and a fingerprint scanner to enter.
	•	Exam tip: If scenario says “reduce password attacks” or “prevent stolen password misuse” → Answer is MFA.

⸻

👑 Privileged Access Management (PAM)

What it is: Special handling of admin accounts (root, domain admin).
	•	When to use: For IT staff, cloud admins, or anyone with high-level rights.
	•	Why: If an admin account is hacked, attacker owns everything. PAM reduces risk by:
	•	Giving admins only temporary rights (Just-in-Time).
	•	Storing passwords in vaults (no one sees them).
	•	Using ephemeral credentials (self-destruct after use).
	•	Big picture analogy: Like checking out the master key to a building only for 1 hour, then the key melts away.
	•	Exam tip: If scenario says “limit exposure of admin accounts” or “temporary elevated rights” → Answer is PAM.

⸻

🗂️ Access Control Models

These are philosophies for “who can access what.”
	•	MAC (Mandatory): Based on clearance labels. Think military.
	•	DAC (Discretionary): Owner decides. Think Windows folder “share” button.
	•	RBAC (Role-Based): Based on your job title/role. Think “HR group has HR folder access”.
	•	Rule-Based: Based on system rules. Think firewalls, ACLs.
	•	ABAC (Attribute-Based): Based on many attributes (location, device, time). Think cloud apps.
	•	Exam tip:
	•	Military/clearance? → MAC
	•	File owner grants access? → DAC
	•	Groups/jobs? → RBAC
	•	If/else rules? → Rule-based
	•	Cloud fine-grained? → ABAC

⸻

📡 LDAP, SAML, OAuth, OpenID Connect (the ones confusing you)

Think of these as languages/protocols different apps use to talk about “who you are”:
	•	LDAP (Directory phonebook):
	•	Like a company’s phonebook → stores users, passwords, groups.
	•	Example: When you log into Windows domain, it checks LDAP.
	•	Exam tip: If scenario says “query user database” → LDAP.
	•	SAML (Enterprise SSO ticket):
	•	XML-based “passport” for web apps.
	•	Example: You log into your company portal → click Salesforce → already logged in.
	•	Exam tip: If scenario says “web SSO with a standard” → SAML.
	•	OAuth (Delegated permission):
	•	Lets one app act on your behalf without sharing your password.
	•	Example: You let a fitness app post to your Twitter without giving it your Twitter password.
	•	Exam tip: If scenario says “grant access without sharing creds” → OAuth.
	•	OpenID Connect (Who you are, built on OAuth):
	•	Adds authentication (identity) on top of OAuth.
	•	Example: “Sign in with Google.” OAuth allows access; OpenID proves you are really you.
	•	Exam tip: If scenario says “authentication on top of OAuth” → OpenID Connect.

⸻

📝 TL;DR Exam Strategy
	•	IAM = Who gets what identity & access (the whole framework).
	•	MFA = Stop password-only hacks.
	•	PAM = Protect admin/root accounts.
	•	Access models = Philosophies (MAC, DAC, RBAC, ABAC).
	•	LDAP/SAML/OAuth/OIDC = Protocols that enable IAM in real life.

