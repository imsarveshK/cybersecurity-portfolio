# Nmap Post Port Scans

*Path:* TryHackMe → Junior Penetration Tester → Nmap → Nmap Post Port Scans

---

# Assessment Goal

Develop a practical understanding of the advanced activities performed after identifying open ports, including:

- Service Version Detection
- Operating System Detection
- Traceroute Analysis
- Nmap Scripting Engine (NSE)
- Saving and Exporting Scan Results

These techniques transform simple port discovery into comprehensive service enumeration and reconnaissance.

---

# Post-Scan Methodology

```text
Open Ports Identified
          │
          ▼
Service Detection
          │
          ▼
OS Fingerprinting
          │
          ▼
Network Path Discovery
          │
          ▼
Script-Based Enumeration
          │
          ▼
Output Documentation
          │
          ▼
Attack Surface Assessment
```

The objective of post-port scanning is to collect intelligence about the target system and prepare for further enumeration or vulnerability assessment.

---

# Task 2 – Service Detection

Once open ports are discovered, the next step is identifying the services running on those ports and their versions.

## Command

```bash
nmap -sV target.thm
```

## Example Output

```text
22/tcp   open   ssh      OpenSSH 8.2
80/tcp   open   http     Apache httpd 2.4.41
3306/tcp open   mysql    MySQL 5.7
```

---

## How Service Detection Works

```text
Open Port
     │
     ▼
Send Probe
     │
     ▼
Receive Banner
     │
     ▼
Compare Signature
     │
     ▼
Identify Service & Version
```

---

## Information Gathered

- Service Name
- Software Version
- Product Information
- Protocol Details
- Potential Vulnerabilities

### Engineering Observation

Knowing the exact service version is extremely valuable because vulnerabilities are usually tied to specific versions.

Example:

```text
Apache 2.4.49
        │
        ▼
Known Path Traversal Vulnerability
```

Therefore, service detection significantly improves vulnerability assessment.

---

# Version Intensity

Nmap allows controlling how aggressively it performs version detection.

## Command

```bash
nmap -sV --version-intensity 5 target.thm
```

Values range from:

| Level | Description |
|--------|-------------|
| 0 | Least aggressive |
| 9 | Most aggressive |

### Engineering Observation

Higher intensity increases accuracy but also increases:

- Scan time
- Network traffic
- Detection probability

---

# Task 3 – OS Detection and Traceroute

# Operating System Detection

Nmap can determine the probable operating system of a target machine.

## Command

```bash
sudo nmap -O target.thm
```

## Example Output

```text
OS details:
Linux 5.X
Windows Server 2019
FreeBSD
```

---

## How OS Detection Works

```text
TCP Probes
      │
      ▼
ICMP Responses
      │
      ▼
TTL Analysis
      │
      ▼
TCP Window Analysis
      │
      ▼
Fingerprint Comparison
      │
      ▼
Operating System Identification
```

---

## Information Gathered

- Operating System Family
- Kernel Version
- Device Type
- Network Distance

### Engineering Observation

OS detection helps attackers and defenders understand:

- Available attack vectors
- Patch requirements
- System architecture
- Security posture

However, firewalls and packet filtering can reduce fingerprint accuracy.

---

# Traceroute

Traceroute discovers the path taken by packets between the scanner and the target.

## Command

```bash
nmap --traceroute target.thm
```

---

## How Traceroute Works

```text
Scanner
   │
Router 1
   │
Router 2
   │
Firewall
   │
Target System
```

---

## Information Gathered

- Number of hops
- Intermediate routers
- Network topology
- Possible filtering devices

### Engineering Observation

Traceroute is useful for:

- Network mapping
- Identifying security boundaries
- Measuring latency
- Troubleshooting connectivity issues

---

# Combined OS Detection and Traceroute

## Command

```bash
sudo nmap -A target.thm
```

This command performs:

- Service Detection
- OS Detection
- Script Scanning
- Traceroute

### Engineering Observation

`-A` is powerful but noisy and easily detected by security monitoring systems.

---

# Task 4 – Nmap Scripting Engine (NSE)

The Nmap Scripting Engine extends Nmap's capabilities using Lua scripts.

---

# Basic NSE Scan

## Command

```bash
nmap --script default target.thm
```

---

## NSE Workflow

```text
Target Host
      │
      ▼
Execute Script
      │
      ▼
Collect Information
      │
      ▼
Display Results
```

---

# Categories of NSE Scripts

| Category | Purpose |
|-----------|----------|
| safe | Non-intrusive scripts |
| discovery | Information gathering |
| auth | Authentication testing |
| vuln | Vulnerability detection |
| brute | Password attacks |
| malware | Malware detection |
| dos | Denial of Service testing |

---

# Example Scripts

## HTTP Title Detection

```bash
nmap --script http-title target.thm
```

## FTP Anonymous Login

```bash
nmap --script ftp-anon target.thm
```

## SMB Enumeration

```bash
nmap --script smb-enum-shares target.thm
```

---

# Vulnerability Scan

```bash
nmap --script vuln target.thm
```

### Engineering Observation

NSE transforms Nmap from a simple scanner into a powerful reconnaissance and vulnerability assessment platform.

However, some scripts are intrusive and should only be executed in authorized environments.

---

# Task 5 – Saving the Output

Documenting scan results is essential during penetration testing.

---

# Normal Output

## Command

```bash
nmap target.thm -oN scan.txt
```

Produces:

```text
Human-readable report
```

---

# XML Output

## Command

```bash
nmap target.thm -oX scan.xml
```

Produces:

```text
Machine-readable report
```

Useful for importing into:

- Metasploit
- Nessus
- Security dashboards

---

# Grepable Output

## Command

```bash
nmap target.thm -oG scan.gnmap
```

Produces:

```text
Searchable text format
```

---

# Save All Formats Simultaneously

## Command

```bash
nmap target.thm -oA full_scan
```

Generates:

```text
full_scan.nmap
full_scan.xml
full_scan.gnmap
```

---

## Output Workflow

```text
Nmap Scan
     │
     ▼
Save Results
     │
     ├── .nmap
     ├── .xml
     └── .gnmap
```

---

### Engineering Observation

Saving outputs provides:

- Evidence collection
- Report generation
- Future analysis
- Tool integration
- Reproducibility

Professional penetration tests always maintain organized scan documentation.

---

# Post Port Scan Intelligence Correlation

```text
Port Discovery
      │
      ▼
Service Detection
      │
      ▼
OS Fingerprinting
      │
      ▼
Traceroute Analysis
      │
      ▼
NSE Enumeration
      │
      ▼
Output Documentation
      │
      ▼
Complete Target Intelligence
```

---

# Engineering Observations

- Open ports alone provide limited information.
- Service versions reveal possible vulnerabilities.
- OS detection helps identify attack vectors.
- Traceroute exposes network topology.
- NSE automates advanced enumeration.
- Saving results is essential for professional reporting.

---

# Operational Security Considerations

Advanced scans are much more detectable than simple port scans.

Potential detection sources include:

- Firewall logs
- IDS/IPS alerts
- SIEM platforms
- Endpoint security solutions
- Network behavior analytics

Aggressive scanning should only be performed within authorized environments.

---

# Defensive Engineering Perspective

Organizations should:

- Hide unnecessary service banners.
- Restrict exposed services.
- Monitor reconnaissance activities.
- Disable unused protocols.
- Patch outdated software versions.
- Review network paths and firewall configurations.
- Log and analyze scanning activity.

---

# Key Technical Takeaways

- Service detection identifies software and versions.
- OS fingerprinting reveals system information.
- Traceroute maps network paths.
- NSE enables automated enumeration and vulnerability detection.
- Saving outputs improves reporting and future analysis.
- Combining post-scan techniques provides complete target intelligence.

---

# Technologies & Tools Practiced

- Nmap Service Detection (`-sV`)
- OS Detection (`-O`)
- Traceroute (`--traceroute`)
- Aggressive Scan (`-A`)
- Nmap Scripting Engine (`--script`)
- Output Formats (`-oN`, `-oX`, `-oG`, `-oA`)
- Service Enumeration
- Network Reconnaissance
- Vulnerability Assessment
