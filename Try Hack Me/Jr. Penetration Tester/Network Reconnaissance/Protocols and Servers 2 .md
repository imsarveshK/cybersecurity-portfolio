# Protocols and Servers 2

**Path:** TryHackMe → Junior Penetration Tester → Network Reconnaissance

---

# Assessment Goal

Analyze common network attack techniques against insecure communication channels and understand how modern cryptographic protocols and secure administration mechanisms mitigate interception, credential theft, and unauthorized access risks.

---

# Security Assessment Methodology

The assessment focused on evaluating how attackers exploit unprotected network communications and how secure protocols defend against these threats.

```text
Network Communication
        │
        ▼
Traffic Observation
(Sniffing)
        │
        ▼
Traffic Manipulation
(MITM)
        │
        ▼
Encryption Protection
(TLS)
        │
        ▼
Secure Administration
(SSH)
        │
        ▼
Authentication Attacks
(Password Attacks)
        │
        ▼
Security Evaluation
```

Understanding both attack techniques and defensive technologies is essential for designing resilient network architectures and secure communication systems.

---

# Technical Analysis

## Sniffing Attack

Packet sniffing involves capturing network traffic to observe data exchanged between systems.

Common tools:

```bash
tcpdump
wireshark
```

Information gathered:

* Network communications
* Authentication requests
* Protocol usage
* User activity patterns
* Unencrypted sensitive data

### Engineering Observation

The effectiveness of sniffing depends heavily on whether communication channels are encrypted. Protocols such as Telnet, FTP, and HTTP expose valuable information directly within captured packets, whereas properly encrypted traffic significantly reduces attacker visibility.

---

## Man-in-the-Middle (MITM) Attack

A MITM attack occurs when an attacker positions themselves between two communicating systems and intercepts traffic flowing between them.

Attack objectives:

* Traffic interception
* Credential theft
* Session hijacking
* Traffic manipulation
* Data modification

Example attack flow:

```text
Victim
   │
   ▼
Attacker
   │
   ▼
Server
```

### Engineering Observation

MITM attacks exploit trust relationships rather than vulnerabilities in application logic. Without strong encryption and certificate validation mechanisms, users often remain unaware that communication has been intercepted.

---

## Transport Layer Security (TLS)

TLS provides encryption, integrity verification, and authentication for network communications.

Example secure communication:

```text
Client
   │
TLS Handshake
   │
   ▼
Encrypted Session
   │
   ▼
Server
```

Security benefits:

* Data confidentiality
* Integrity protection
* Authentication
* Resistance to eavesdropping
* MITM mitigation

### Engineering Observation

TLS serves as one of the most critical security controls on modern networks. Proper certificate validation is equally important as encryption itself, since accepting invalid certificates can undermine TLS protections entirely.

---

## Secure Shell (SSH)

SSH is a secure remote administration protocol that replaces insecure protocols such as Telnet.

Example:

```bash
ssh user@target.thm
```

Information gathered:

* Remote administrative access
* Secure command execution
* Secure file transfers
* Identity verification

### Engineering Observation

SSH provides encrypted authentication and session management, making it significantly more secure than legacy remote administration protocols. Public-key authentication further strengthens security by reducing reliance on passwords.

---

## Password Attacks

Password attacks target authentication systems by attempting to obtain valid credentials through guessing, reuse, or brute-force techniques.

Common attack methods:

* Brute force attacks
* Dictionary attacks
* Password spraying
* Credential stuffing

Example:

```text
Username
    │
    ▼
Authentication Attempts
    │
    ▼
Access Granted / Denied
```

### Engineering Observation

Password attacks remain effective because human behavior often creates weak authentication practices. Even strong protocols can be compromised if weak credentials are used. Authentication security must therefore complement network security controls.

---

# Attack and Defense Relationship Analysis

Each topic demonstrates a different stage in the security lifecycle.

```text
Sniffing
      │
      ▼
Traffic Observation

MITM
      │
      ▼
Traffic Interception

TLS
      │
      ▼
Communication Protection

SSH
      │
      ▼
Secure Administration

Password Attacks
      │
      ▼
Authentication Threats

═══════════════════════

Combined Result

Secure Network Communication Model
```

The assessment demonstrates how modern security protocols evolved specifically to address weaknesses exploited by interception and credential-based attacks.

---

# Engineering Observations

Several important observations emerged during this assessment:

* Network traffic should always be assumed observable on untrusted networks.
* Encryption significantly reduces the effectiveness of packet capture attacks.
* MITM attacks frequently target user trust rather than technical weaknesses.
* Secure protocols such as TLS and SSH mitigate many legacy network security risks.
* Authentication remains a critical security dependency regardless of protocol strength.
* Weak credentials can undermine otherwise secure communication channels.

---

# Operational Security Considerations

Organizations should continuously evaluate both communication security and authentication resilience.

Security considerations include:

* Encryption enforcement
* Certificate management
* Secure remote administration
* Credential protection
* Multi-factor authentication
* Monitoring authentication failures
* Detection of anomalous login activity

Communication security and identity security must be treated as interconnected controls.

---

# Defensive Engineering Perspective

Organizations should implement layered protections against interception and credential attacks.

Recommended defensive measures include:

* Enforce TLS across all web services.
* Replace insecure administration protocols with SSH.
* Validate and monitor certificate infrastructure.
* Deploy Multi-Factor Authentication (MFA).
* Implement account lockout and rate-limiting controls.
* Monitor for credential stuffing and brute-force attempts.
* Encrypt sensitive communications end-to-end.
* Conduct regular password hygiene assessments.

---

# Key Technical Takeaways

* Sniffing attacks exploit visibility into network traffic.
* MITM attacks intercept and potentially alter communications between systems.
* TLS protects confidentiality, integrity, and authenticity of network communications.
* SSH provides secure remote administration capabilities.
* Strong encryption reduces exposure to network interception attacks.
* Authentication security remains essential even when communications are encrypted.
* Modern network security relies on combining encryption, identity protection, and monitoring controls.

---

# Technologies & Protocols Practiced

* Packet Sniffing Concepts
* Man-in-the-Middle (MITM)
* TLS
* SSH
* Authentication Security
* Password Attack Methodologies

---

