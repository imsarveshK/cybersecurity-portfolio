# Linux System Hardening

## Objective
Understand the fundamentals of Linux system hardening and learn how to secure Linux systems by reducing attack surfaces, enforcing security controls, and applying defensive best practices.

---

## Concepts Covered
- Physical security
- Filesystem partitioning & encryption
- Firewall configuration
- Remote access security
- Securing user accounts
- Software & service hardening
- Update & upgrade policies
- Audit & log configuration

---

## Linux System Hardening Overview

Linux system hardening is the process of improving system security by:
- Reducing vulnerabilities
- Restricting unnecessary access
- Securing services
- Applying defensive configurations
- Monitoring system activity

The goal is to minimize attack surface and improve overall system resilience.

---

## Physical Security

Physical security protects systems from unauthorized physical access.

Examples:
- Securing servers in restricted areas
- BIOS/UEFI protection
- Preventing unauthorized device access
- Hardware theft prevention

Physical access can lead to full system compromise if not controlled properly.

---

## Filesystem Partitioning & Encryption

Separating filesystems improves security and system management.

Benefits include:
- Limiting attack impact
- Isolating sensitive data
- Improving access control

Encryption helps protect:
- Sensitive files
- User data
- Backup storage

Examples:
- Disk encryption
- Encrypted partitions
- Secure storage configurations

## Performed Linux disk encryption and secure volume management using LUKS and cryptsetup, including opening encrypted containers, mounting secure volumes, and accessing protected filesystems. Gained practical understanding of Linux data-at-rest protection and secure storage handling.

<img width="2301" height="701" alt="Screenshot 2026-05-23 182819" src="https://github.com/user-attachments/assets/12c1f0ff-df63-4389-beee-fb3eeac6cba3" />

---

## Firewall Configuration

Firewalls control incoming and outgoing network traffic.

Common Linux firewall tools:
- UFW
- iptables
- firewalld

Typical hardening actions:
- Blocking unnecessary ports
- Restricting remote access
- Allowing only trusted services

---

## Remote Access Security

Remote access services such as SSH should be configured securely.

Common hardening measures:
- Disable root login
- Use SSH key authentication
- Restrict login attempts
- Limit remote administrative access

Secure remote access reduces unauthorized access risks.

---

## Securing User Accounts

Account security is critical for Linux hardening.

Best practices include:
- Strong password policies
- Least privilege access
- Removing unused accounts
- Restricting sudo permissions
- Enabling MFA where possible

---

## Software & Service Hardening

Unused or insecure software increases attack surface.

Hardening measures include:
- Disabling unnecessary services
- Removing unused applications
- Securing running services
- Restricting exposed ports

Only required services should remain active.

---

## Update & Upgrade Policies

Regular updates help:
- Fix vulnerabilities
- Improve system stability
- Reduce exploit risks

Patch management is essential for maintaining secure Linux infrastructure.

---

## Audit & Log Configuration

System logging and auditing improve visibility into:
- Authentication attempts
- User activity
- System changes
- Security incidents

Common logging practices:
- Monitoring authentication logs
- Reviewing suspicious activity
- Configuring audit policies

---

## Security Concepts Mentioned

```text
Linux Hardening
Filesystem Encryption
Firewall Configuration
SSH Security
Least Privilege
Patch Management
Audit Logging
Access Control
```

---

## Best Practices

Recommended approaches:
- Disable unnecessary services
- Restrict administrative access
- Apply least privilege principles
- Enable firewall protections
- Keep systems updated regularly
- Monitor logs continuously
- Use secure authentication methods

---

## Key Learnings
- Linux hardening reduces attack surface significantly
- Physical security is important for overall system protection
- Secure remote access reduces unauthorized entry risks
- Logging and auditing improve security visibility
- Regular updates and service hardening strengthen infrastructure security

---

## Screenshot of room completion

<img width="1842" height="789" alt="Screenshot 2026-05-23 191848" src="https://github.com/user-attachments/assets/60a89ccc-cacd-4a57-9e10-30dfbfaf6e90" />

---

## Notes
This room introduced Linux system hardening concepts and demonstrated how organizations secure Linux environments through secure configurations, firewall management, account security, encryption, auditing, and defensive best practices.
