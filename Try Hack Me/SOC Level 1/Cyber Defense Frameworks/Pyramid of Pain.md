# Pyramid of Pain

## Objective
Understand the Pyramid of Pain model and learn how different Indicators of Compromise (IOCs) affect attackers when defenders detect and block malicious activity.

---

## Concepts Covered
- Pyramid of Pain
- Indicators of Compromise (IOCs)
- Threat hunting
- Detection engineering
- Adversary behavior
- Defensive security strategies

---

## Pyramid of Pain Overview

The Pyramid of Pain is a cybersecurity model created by David J. Bianco that demonstrates how difficult it becomes for attackers when defenders detect and block different types of indicators.

The higher defenders move up the pyramid, the more disruption is caused to attackers.

---

## Levels of the Pyramid of Pain

### Hash Values
File hashes used to identify known malicious files.

Examples:
- MD5
- SHA1
- SHA256

Attackers can easily modify malware to generate new hashes, making these indicators easy to bypass.

---

### IP Addresses
Malicious IP addresses used by attackers during operations.

Defenders may:
- Block malicious IPs
- Monitor suspicious connections

Attackers can change infrastructure relatively easily.

---

### Domain Names
Malicious domains used for phishing, malware delivery, or command-and-control (C2) communication.

Defenders can:
- Block domains
- Monitor DNS requests

Attackers may register new domains to evade detection.

---

### Network / Host Artifacts
Observable indicators left behind during attacks.

Examples:
- Registry changes
- File paths
- User-agent strings
- Process execution patterns

These are more difficult for attackers to modify consistently.

---

### Tools
Software or frameworks used by attackers during operations.

Examples:
- PowerShell abuse
- Mimikatz
- Cobalt Strike

Detecting attacker tools increases operational difficulty for adversaries.

---

### TTPs (Tactics, Techniques, and Procedures)

Behavioral patterns used by attackers during campaigns.

Examples:
- Credential dumping
- Lateral movement
- Phishing techniques
- Privilege escalation

Detecting TTPs causes the greatest disruption because attackers must change operational behavior.

---

## Importance for SOC Analysts

SOC analysts use the Pyramid of Pain to:
- Improve detection strategies
- Prioritize high-value detections
- Focus on attacker behavior instead of simple indicators
- Strengthen threat hunting capabilities

---

## Defensive Strategies

Recommended approaches:
- Detect attacker behaviors
- Monitor suspicious activity patterns
- Build detections around TTPs
- Correlate multiple indicators
- Continuously improve threat detection rules

---

## Identified the tires of Pyramid of Pain-

<img width="764" height="616" alt="Screenshot 2026-05-09 210904" src="https://github.com/user-attachments/assets/5342d580-d787-4441-95ca-77bc5ab63b00" />

<img width="763" height="662" alt="Screenshot 2026-05-09 211137" src="https://github.com/user-attachments/assets/c2da2dd0-90e3-4385-b43f-0432e58146ff" />


---

## Key Learnings
- Simple indicators like hashes and IPs are easy for attackers to change
- Detecting attacker behavior causes greater operational disruption
- TTP-based detection is more effective than IOC-only detection
- The Pyramid of Pain helps prioritize defensive strategies
- Behavioral monitoring improves long-term detection capabilities

---

## Screenshot of room completion

<img width="1279" height="659" alt="Screenshot 2026-05-09 211225" src="https://github.com/user-attachments/assets/15820155-2204-4995-9606-40ec95f6cc98" />


---

## Notes
This room introduced the Pyramid of Pain framework and demonstrated how defenders can increase attacker difficulty by focusing on higher-level behavioral indicators and adversary tactics instead of relying solely on basic IOCs.
