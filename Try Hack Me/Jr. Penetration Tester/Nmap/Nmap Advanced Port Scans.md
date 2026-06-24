# Nmap Advanced Port Scans

**Path:** TryHackMe → Junior Penetration Tester → Nmap

---

# Assessment Goal

Develop an understanding of advanced Nmap scanning techniques used to evade detection mechanisms, analyze firewall behavior, disguise scanner identity, and perform reconnaissance against protected network environments.

---

# Scanning Methodology

Advanced port scanning leverages TCP flag manipulation, traffic obfuscation, packet fragmentation, and indirect communication methods to gather information while minimizing visibility.

```text
Evasive Entry Point
          │
          ▼
Flag Anomaly Manipulation
(Null / FIN / Xmas / Maimon)
          │
          ▼
Boundary Penetration
(ACK / Window Scanning)
          │
          ▼
Identity Masking
(Spoofing / Decoys)
          │
          ▼
Perimeter Deception
(Packet Fragmentation)
          │
          ▼
Zero-Trace Reconnaissance
(Idle / Zombie Scanning)
```

---

# TCP Null Scan, FIN Scan, and Xmas Scan

## Overview

Null, FIN, and Xmas scans exploit RFC 793 TCP behavior by transmitting packets with unusual flag combinations rather than initiating a traditional TCP handshake.

```text
Open Port   → No Response
Closed Port → TCP RST Response
```

## Null Scan

A Null Scan sends TCP packets without any control flags enabled.

```bash
sudo nmap -sN target.thm
```

### Key Findings

* No TCP flags are set.
* Closed ports return RST packets.
* Open ports often ignore the packet.
* Useful against simple stateless filtering devices.

---

## FIN Scan

A FIN Scan sends packets containing only the FIN flag.

```bash
sudo nmap -sF target.thm
```

### Key Findings

* Relies on RFC 793 behavior.
* May bypass devices focused solely on SYN traffic.
* Commonly used for stealth reconnaissance.

---

## Xmas Scan

An Xmas Scan transmits packets with FIN, PSH, and URG flags enabled.

```bash
sudo nmap -sX target.thm
```

### Key Findings

* Produces a distinctive TCP flag pattern.
* Closed ports typically respond with RST packets.
* Open ports generally remain silent.

### Engineering Observation

* Most effective against Unix and Linux systems.
* Microsoft Windows commonly returns RST packets regardless of port state.

---

# TCP Maimon Scan

## Overview

The Maimon Scan uses FIN and ACK flags simultaneously to identify systems exhibiting BSD-derived TCP behavior.

```bash
sudo nmap -sM target.thm
```

### Key Findings

* Sends FIN and ACK flags together.
* Certain BSD implementations ignore packets on open ports.
* Closed ports usually return RST packets.

### Engineering Observation

* Valuable for fingerprinting legacy TCP/IP implementations.
* Less reliable on modern operating systems.

---

# TCP ACK, Window, and Custom Scan

## ACK Scan

An ACK Scan evaluates firewall filtering behavior rather than determining whether ports are open.

```bash
sudo nmap -sA target.thm
```

### Interpretation

```text
RST Response → Unfiltered
No Response  → Filtered
ICMP Error   → Filtered
```

### Key Findings

* Maps firewall rule enforcement.
* Identifies filtering boundaries.
* Does not directly reveal open ports.

---

## Window Scan

A Window Scan analyzes TCP Window size values returned by the target.

```bash
sudo nmap -sW target.thm
```

### Interpretation

```text
Window > 0 → Open Port
Window = 0 → Closed Port
```

### Key Findings

* Depends on operating system implementation.
* Useful for advanced TCP stack analysis.

---

## Custom TCP Flag Scanning

Custom scans allow arbitrary combinations of TCP flags.

```bash
sudo nmap --scanflags SYNRSTURG target.thm
```

### Key Findings

* Provides complete control over packet construction.
* Useful for testing firewall and IDS behavior.
* Enables highly specialized reconnaissance scenarios.

---

# Spoofing and Decoys

## Source IP Spoofing

Source IP spoofing replaces the real source address with a forged address.

```bash
sudo nmap -S SPOOFED_IP target.thm
```

### Key Findings

* Responses are sent to the spoofed host.
* Useful for validating anti-spoofing protections.
* Requires additional mechanisms to observe responses.

---

## Decoy Scanning

Decoy scanning mixes legitimate scan traffic with multiple fabricated scanner identities.

```bash
sudo nmap -D DECOY1,DECOY2,ME,DECOY3 target.thm
```

### Key Findings

* Obscures the true scan origin.
* Complicates log attribution.
* Increases uncertainty during forensic investigations.

---

# Packet Fragmentation

## Overview

Packet fragmentation divides packet headers into smaller fragments to challenge packet inspection engines.

### Standard Fragmentation

```bash
sudo nmap -f target.thm
```

### Deep Fragmentation

```bash
sudo nmap -ff target.thm
```

### Key Findings

* Forces packet reassembly.
* May bypass legacy signature-based inspection systems.
* Useful for validating defensive normalization controls.

### Engineering Observation

Modern IDS and NGFW solutions generally reassemble fragmented packets before inspection, reducing the effectiveness of this technique.

---

# Idle/Zombie Scanning

## Overview

Idle scanning performs reconnaissance indirectly through a third-party system, preventing direct communication between the attacker and target.

```bash
sudo nmap -sI ZOMBIE_IP target.thm
```

## Workflow

```text
Attacker
   │
   ▼
Zombie Host
   │
   ▼
Target System
```

### Interpretation

```text
IPID Increase by 2 → Open Port
IPID Increase by 1 → Closed Port
```

### Key Findings

* Provides exceptional anonymity.
* Relies on predictable IP ID sequences.
* Eliminates direct attacker-to-target communication.

### Engineering Observation

Randomized IP ID generation in modern operating systems significantly reduces the practicality of idle scanning.

---

# Scan Diagnostics and Visibility

## Overview

Nmap provides diagnostic flags that improve result interpretation and troubleshooting.

```bash
sudo nmap -sS --reason -vv target.thm
```

## Reason Tracking

```text
received syn-ack
received rst-ack
received icmp unreachable
```

### Benefits

* Displays the exact reason behind port-state classification.
* Simplifies troubleshooting.
* Improves scan validation.

---

## Verbose Output

```bash
-v
-vv
```

### Benefits

* Provides real-time status updates.
* Displays additional scan details.
* Enhances visibility during large assessments.

---

# Key Technical Takeaways

* Null, FIN, and Xmas scans exploit RFC 793 TCP behavior.
* Maimon scans target BSD-specific TCP implementations.
* ACK scans reveal firewall filtering policies.
* Window scans leverage TCP window size differences.
* Custom scans allow arbitrary TCP flag combinations.
* Spoofing and decoys obscure scanner attribution.
* Packet fragmentation challenges legacy inspection systems.
* Idle scanning enables indirect reconnaissance through third-party hosts.
* Diagnostic flags improve visibility into scan decision-making.

---

# Technologies and Platforms Practiced

* Nmap Advanced Evasion Techniques
* Null Scan (-sN)
* FIN Scan (-sF)
* Xmas Scan (-sX)
* Maimon Scan (-sM)
* ACK Scan (-sA)
* Window Scan (-sW)
* Custom TCP Flag Scanning (--scanflags)
* Source IP Spoofing (-S)
* Decoy Scanning (-D)
* Packet Fragmentation (-f, -ff)
* Idle/Zombie Scanning (-sI)
* Diagnostic Analysis (--reason, -vv)
