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
