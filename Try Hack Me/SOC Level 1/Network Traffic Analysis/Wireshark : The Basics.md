# Wireshark: The Basics

## Objective
Learn the fundamentals of Wireshark and understand how SOC analysts use packet analysis to inspect network traffic, investigate suspicious activity, and analyze communication protocols.

---

## Concepts Covered
- Wireshark fundamentals
- Packet analysis
- Network traffic inspection
- Protocol analysis
- Packet filtering
- Network investigations

---

## Wireshark Overview

Wireshark is a network protocol analyzer used to:
- Capture network packets
- Inspect network communications
- Analyze protocols
- Investigate suspicious traffic
- Troubleshoot network issues

It is widely used by SOC analysts and security professionals during network investigations.

---

## Packet Analysis

Wireshark allows analysts to inspect:
- Source and destination IP addresses
- Protocols
- Ports
- Packet payloads
- Communication behavior

Packet inspection helps identify suspicious or malicious activity on a network.

---

## Common Protocols Observed

The room covered several important protocols including:
- TCP
- UDP
- HTTP
- HTTPS
- DNS
- ICMP

Understanding protocol behavior is essential for identifying abnormal traffic patterns.

---

## Packet Filtering

Wireshark supports display filters to simplify investigations.

Examples of common filters:

```wireshark
ip.addr == 10.10.10.5
```

```wireshark
http.request
```

```wireshark
dns
```

```wireshark
tcp.port == 80
```

Filters help analysts isolate relevant traffic quickly.

---

## Network Investigation Workflow

Typical packet analysis process:
- Capture or open PCAP files
- Apply filters
- Review suspicious traffic
- Analyze communication patterns
- Identify Indicators of Compromise (IOCs)

---

## Indicators of Suspicious Activity

Examples include:
- Unusual outbound traffic
- Suspicious DNS requests
- Repeated failed connections
- Beaconing behavior
- Communication with malicious IPs

---

## Best Practices

Recommended approaches:
- Use filters to narrow investigations
- Analyze protocols carefully
- Monitor unusual communication patterns
- Validate suspicious traffic with additional context
- Correlate traffic with security alerts

---

## Key Learnings
- Wireshark provides deep visibility into network traffic
- Packet filtering improves investigation efficiency
- Protocol analysis helps identify malicious behavior
- Network traffic analysis supports incident investigations
- Packet captures contain valuable forensic evidence

---

## Screenshot of room completion

<img width="1109" height="459" alt="Screenshot 2026-05-12 183722" src="https://github.com/user-attachments/assets/276cceca-7f5d-4f15-a44b-fcb3a4346012" />


---

## Notes
This room introduced the fundamentals of Wireshark and demonstrated how SOC analysts use packet analysis and protocol inspection to investigate suspicious network activity and support security investigations.
