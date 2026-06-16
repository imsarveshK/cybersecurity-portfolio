# Lab Logbook: Cyber Kill Chain
**Path:** TryHackMe -> Junior Penetration Tester -> Penetration Testing Foundations

## 🎯 Cyber Defense Framework Objective
To analyze the traditional Lockheed Martin Cyber Kill Chain framework, break down the seven distinct phases of an adversarial attack lifecycle, and identify the exact defensive mechanisms and telemetry required to disrupt an incident at each stage.

## ⚙️ Core Concepts Evaluated
- **Adversarial Lifecycle:** Mapping step-by-step attacker progression from initial recon to final payload objectives.
- **Defensive Line-of-Sight:** Identifying where firewalls, EDR, SIEM, and access controls map to specific attack vectors.
- **The Golden Rule:** The earlier an attack is disrupted in the kill chain, the lower the cost, complexity, and structural impact of remediation.

---

## 🔍 Technical Analysis & Phase Breakdown

An attack is not a single cataclysmic event; it is a chain of dependent phases. Breaking any single link in this chain completely neutralizes the adversary's operational objective.

```text
[Reconnaissance] ──> [Weaponization] ──> [Delivery] ──> [Exploitation] ──> [Installation] ──> [C2] ──> [Actions on Objectives]
```

### 1. Reconnaissance (Information Gathering)
   
The adversary identifies targets, harvests public OSINT data, scans infrastructure boundaries, and maps vulnerabilities.

Offensive Vector: Harvesting email addresses via LinkedIn, executing passive DNS lookups, or running active network sweeps using tools like Nmap.

Defensive Countermeasure: Analyzing firewall/IDS logs for anomalous scanning patterns, configuring aggressive rate-limiting, and minimizing public-facing corporate metadata exposure.

### 2. Weaponization (Payload Construction)
   
The attacker couples an exploit with a malicious payload (e.g., creating an infected macro inside an Excel spreadsheet or weaponizing a specific PDF). This phase happens entirely on the attacker's infrastructure.

Offensive Vector: Generating a reverse shell payload using msfvenom and embedding it into an application binary.

Defensive Countermeasure: This phase is invisible to enterprise logging because it happens externally. Defense relies on proactive Threat Intelligence tracking known adversary infrastructure and framework signatures.

### 3. Delivery (Transmission of the Asset)
   
The weaponized payload is transmitted to the target environment via an entry vector.

Offensive Vector: Sending targeted phishing emails with malicious attachments, deploying water-hole attacks, or dropping infected USB drives in a parking lot.

Defensive Countermeasure: Strict Email Gateway protection rules (SPF, DKIM, DMARC validation), proxy content filtering, and user awareness training models.

### 4. Exploitation (Triggering the Malicious Code)
   
The delivered payload triggers, taking advantage of a known software, operating system, or human vulnerability on the host system.

Offensive Vector: The victim double-clicks the attachment, executing a malicious script that capitalizes on unpatched browser vulnerabilities or macro permissions.

Defensive Countermeasure: Rigid Endpoint Detection and Response (EDR) agents, regular patch management cycles to close software flaws, and disabling auto-execution parameters.

### 5. Installation (Establishing Persistence)
   
The payload configures itself to maintain long-term access within the host operating system, ensuring the attacker survives system reboots or logouts.

Offensive Vector: Modifying Windows Registry AutoRun keys, creating malicious Scheduled Tasks, or installing unauthorized background system daemons.

Defensive Countermeasure: Utilizing tools like Microsoft Sysmon to monitor unexpected Registry write anomalies, tracking file integrity modifications, and implementing the Principle of Least Privilege (blocking standard users from writing to system folders).

### 6. Command & Control (C2 - Establishing the Beacon)
   
The compromised host establishes a secure, remote communication channel back to the attacker’s external command infrastructure to receive tactical instructions.

Offensive Vector: Encrypted HTTPS beacons hiding in standard web traffic, DNS tunneling, or utilizing legitimate cloud providers to bypass network egress filters.

Defensive Countermeasure: In-depth Network Traffic Analysis (NTA), DNS query logging to isolate high-frequency or anomalous subdomains, and maintaining strict outbound proxy restrictions.

### 7. Actions on Objectives (The Final Blow)
   
With total control established, the attacker executes their ultimate mission.

Offensive Vector: Exfiltrating intellectual property, wiping target server backups, manipulating financial assets, or dropping ransomware components to lock down infrastructure.

Defensive Countermeasure: Data Loss Prevention (DLP) controls monitoring massive outbound data transfers, proactive endpoint execution blocks for known locker families, and air-gapped immutable backup structures.

### 🛠️ Security Engineering & Blue-Team Takeaways

Defense in Depth Matrix:
Relying on a single boundary control guarantees a breach. True infrastructure engineering requires interlocking visibility—if a firewall misses the Delivery phase, a local host EDR must trigger during the Exploitation phase, and SIEM logic must flag anomalous traffic during the Command & Control phase.

Incident Response Pivot Point:
When triaging an alert inside a SIEM (like Splunk), determining the current Kill Chain phase immediately tells the analyst the severity of the incident. An alert signaling a malicious file download (Delivery) requires a standard desktop isolation protocol; an alert tracking an encrypted out-of-bounds outbound beacon (C2) requires an immediate, high-severity Incident Response declaration.
