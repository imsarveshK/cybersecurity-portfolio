# Nmap Basic Port Scans

**Path:** TryHackMe → Junior Penetration Tester → Network Security Fundamentals

---

# Assessment Goal

Develop a practical understanding of how Nmap performs port discovery, how TCP and UDP services respond to scanning techniques, and how different scan types balance speed, accuracy, stealth, and reliability during network reconnaissance.

---

# Scanning Methodology

Port scanning is performed after live hosts have been identified. The objective is to determine which services are accessible and how those services respond to network probes.

```text
Live Host
      │
      ▼
Port Identification
      │
      ▼
Protocol Analysis
(TCP / UDP)
      │
      ▼
Scan Technique Selection
      │
      ▼
Response Interpretation
      │
      ▼
Service Enumeration
      │
      ▼
Attack Surface Assessment
```

Understanding scan behavior is critical because different scanning techniques generate different network signatures and detection opportunities.

---

# Technical Analysis

## TCP and UDP Ports

Network services communicate through ports, which act as logical communication endpoints.

Common examples:

| Port | Protocol | Service |
|--------|------------|------------|
| 22 | TCP | SSH |
| 25 | TCP | SMTP |
| 53 | UDP/TCP | DNS |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |

Port states commonly observed by Nmap:

| State | Meaning |
|---------|----------|
| Open | Service actively accepts connections |
| Closed | Host reachable but service unavailable |
| Filtered | Firewall or filtering device prevents determination |
| Open\|Filtered | Unable to distinguish between open and filtered |
| Closed\|Filtered | Limited response visibility |

### Engineering Observation

An open port is not automatically a vulnerability. However, every exposed service increases the attack surface and becomes a potential target for further enumeration.

---

## TCP Flags

TCP communication relies on control flags that manage connection establishment and termination.

Important flags:

| Flag | Purpose |
|---------|----------|
| SYN | Initiate connection |
| ACK | Acknowledge receipt |
| FIN | Gracefully terminate connection |
| RST | Reset connection |
| PSH | Push buffered data |
| URG | Urgent data indicator |

Typical TCP three-way handshake:

```text
Client                 Server
  │ ---- SYN -------> │
  │ <--- SYN/ACK ---- │
  │ ---- ACK -------> │
```

### Engineering Observation

Most TCP scanning techniques manipulate flag behavior to determine port state without fully establishing application-level communication.

Understanding TCP flags is essential for interpreting both scan results and defensive monitoring alerts.

---

## TCP Connect Scan

TCP Connect Scan performs a complete three-way handshake with the target service.

Example:

```bash
nmap -sT target.thm
```

Scan process:

```text
SYN
 ▼
SYN/ACK
 ▼
ACK
 ▼
Connection Established
 ▼
Connection Closed
```

Information gathered:

* Open TCP ports
* Service accessibility
* Reachability validation

### Engineering Observation

TCP Connect Scans are highly reliable because the operating system handles the connection process. However, they generate more logs and are easier for security teams to detect.

---

## TCP SYN Scan

TCP SYN Scan performs a partial handshake, commonly referred to as a "half-open" scan.

Example:

```bash
sudo nmap -sS target.thm
```

Scan process:

```text
SYN
 ▼
SYN/ACK
 ▼
RST
```

Information gathered:

* Open TCP ports
* Service responsiveness
* Reduced scan footprint

### Engineering Observation

SYN Scans are generally faster and more efficient than Connect Scans. Since the connection is never fully established, they often generate less application-level logging while still providing accurate port state information.

This is one of the most commonly used reconnaissance techniques in penetration testing.

---

## UDP Scan

UDP services do not establish connections like TCP, making discovery significantly more challenging.

Example:

```bash
sudo nmap -sU target.thm
```

Response behavior:

```text
UDP Probe
      │
      ├── ICMP Port Unreachable → Closed
      │
      ├── UDP Response → Open
      │
      └── No Response → Open|Filtered
```

Information gathered:

* DNS services
* SNMP services
* DHCP-related services
* Other UDP-based applications

### Engineering Observation

UDP scanning is considerably slower than TCP scanning because the absence of responses must often be interpreted indirectly. Despite this limitation, many critical enterprise services operate exclusively over UDP and cannot be ignored during assessments.

---

## Fine-Tuning Scope and Performance

Nmap allows extensive optimization of scan scope and performance.

Examples:

```bash
nmap -p 22,80,443 target.thm

nmap -F target.thm

nmap -T4 target.thm

nmap --top-ports 100 target.thm
```

Common optimization techniques:

* Target specific ports
* Scan top common ports
* Adjust timing templates
* Limit scan ranges
* Reduce unnecessary probes

### Engineering Observation

Efficient scanning is not about scanning everything. Effective assessments balance coverage, speed, accuracy, and operational impact while remaining within authorized scope.

Overly aggressive scanning may generate excessive noise, trigger defensive controls, or produce unreliable results.

---

# Port Discovery Intelligence Correlation

Each scanning technique contributes unique visibility into the target environment.

```text
Port Analysis
      │
      ▼
Service Exposure

TCP Connect Scan
      │
      ▼
Reliable Validation

TCP SYN Scan
      │
      ▼
Efficient Discovery

UDP Scan
      │
      ▼
Non-TCP Visibility

Performance Tuning
      │
      ▼
Optimized Enumeration

═══════════════════════

Combined Result

Network Service Inventory
```

Accurate service discovery depends on combining multiple scanning techniques rather than relying on a single approach.

---

# Engineering Observations

Several important observations emerged during this assessment:

* Port scanning serves as the foundation for service enumeration.
* Different protocols require different discovery strategies.
* TCP Connect Scans prioritize reliability.
* SYN Scans balance speed and visibility.
* UDP services are more difficult to identify accurately.
* Scan tuning significantly affects efficiency and detection likelihood.
* Understanding TCP behavior improves interpretation of scan results.

---

# Operational Security Considerations

Port scanning generates observable network activity and is frequently monitored by security teams.

Potential detection sources include:

* Firewall logs
* IDS/IPS alerts
* Endpoint detection systems
* SIEM correlation platforms
* Network monitoring solutions

Scan intensity directly influences detection probability.

---

# Defensive Engineering Perspective

Organizations should continuously monitor exposed services and reconnaissance activity.

Recommended defensive measures include:

* Restrict unnecessary service exposure.
* Filter unused ports.
* Monitor SYN scanning behavior.
* Implement IDS/IPS reconnaissance signatures.
* Harden Internet-facing services.
* Review firewall rules regularly.
* Conduct periodic exposure assessments.

---

# Key Technical Takeaways

* Port scanning identifies accessible services on discovered hosts.
* TCP and UDP require different scanning methodologies.
* TCP Connect Scans provide reliable service validation.
* SYN Scans offer faster and more efficient reconnaissance.
* UDP discovery remains challenging due to connectionless communication.
* Scan optimization improves assessment efficiency.
* Understanding scan mechanics improves both offensive and defensive security capabilities.

---

# Technologies & Tools Practiced

* Nmap
* TCP Connect Scan (-sT)
* TCP SYN Scan (-sS)
* UDP Scan (-sU)
* TCP Flags Analysis
* Port Enumeration
* Network Service Discovery

---

