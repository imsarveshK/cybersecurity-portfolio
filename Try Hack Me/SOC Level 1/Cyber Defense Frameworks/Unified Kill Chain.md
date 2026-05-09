# Unified Kill Chain

## Objective
Understand the Unified Kill Chain framework and learn how modern cyber attacks combine elements of the Cyber Kill Chain and MITRE ATT&CK framework to model adversary behavior across the entire attack lifecycle.

---

## Concepts Covered
- Unified Kill Chain
- Adversary lifecycle
- MITRE ATT&CK concepts
- Cyber Kill Chain integration
- Threat detection
- Defensive security strategies

---

## Unified Kill Chain Overview

The Unified Kill Chain is a cybersecurity framework designed to provide a more comprehensive view of modern cyber attacks by combining:
- Lockheed Martin's Cyber Kill Chain
- MITRE ATT&CK techniques

The framework models attacker behavior across the full intrusion lifecycle and helps defenders identify opportunities to detect and disrupt adversaries.

---

## Goals of the Unified Kill Chain

The framework helps organizations:
- Understand attacker behavior
- Improve threat detection
- Strengthen defensive strategies
- Identify attack progression stages
- Reduce attacker success rates

---

## Phases of the Unified Kill Chain

### Initial Foothold
Attackers gain initial access to the target environment.

Examples:
- Phishing
- Exploiting public-facing applications
- Credential theft

---

### Network Propagation
Attackers expand access within the environment.

Examples:
- Lateral movement
- Credential reuse
- Remote service exploitation

---

### Privilege Escalation
Attackers attempt to gain elevated privileges.

Examples:
- Exploiting vulnerabilities
- Credential dumping
- Misconfiguration abuse

---

### Defense Evasion
Attackers attempt to avoid detection.

Examples:
- Log tampering
- Obfuscation
- Disabling security tools

---

### Persistence
Attackers maintain long-term access to compromised systems.

Examples:
- Scheduled tasks
- Registry modifications
- Backdoors

---

### Command and Control (C2)
Compromised systems communicate with attacker infrastructure.

Examples:
- Beaconing traffic
- Remote access channels
- Encrypted communications

---

### Actions on Objectives
Attackers achieve operational goals.

Examples:
- Data exfiltration
- Ransomware deployment
- Service disruption
- Espionage

---

## Relation to MITRE ATT&CK

The Unified Kill Chain incorporates adversary techniques from the MITRE ATT&CK framework to provide:
- Behavioral visibility
- Technique mapping
- Better detection opportunities

This helps defenders understand how attackers operate during different attack phases.

---

## Importance for SOC Analysts

SOC analysts use the Unified Kill Chain to:
- Track attack progression
- Detect suspicious behavior
- Correlate related events
- Improve incident response
- Develop detection strategies

---

## Defensive Strategies

Recommended approaches:
- Monitor attacker behaviors
- Detect lateral movement
- Implement least privilege access
- Harden systems against persistence techniques
- Monitor command-and-control activity
- Use layered security controls

---

## Key Learnings
- Modern attacks involve multiple interconnected stages
- Behavioral detection improves defensive effectiveness
- The Unified Kill Chain extends traditional attack models
- Mapping attacker techniques helps improve SOC visibility
- Layered defenses help disrupt attack progression

---

## Screenshot of room completion

<img width="1112" height="490" alt="Screenshot 2026-05-09 222306" src="https://github.com/user-attachments/assets/f69364b0-f0af-4f8a-876a-d58f426587e6" />


---

## Notes
This room introduced the Unified Kill Chain framework and demonstrated how defenders can model, detect, and disrupt modern cyber attacks across the entire intrusion lifecycle using behavioral analysis and adversary-focused detection strategies.
