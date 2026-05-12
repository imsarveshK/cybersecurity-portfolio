# Wireshark: Packet Operations

## Objective
Learn how to perform packet-level operations in Wireshark, including inspecting packets, following streams, exporting objects, and analyzing network traffic during investigations.

---

## Concepts Covered
- Packet operations
- Packet inspection
- Stream analysis
- Packet filtering
- Exporting objects
- Network traffic investigations

---

## Packet Operations Overview

Wireshark provides several packet operation features that help analysts:
- Inspect individual packets
- Analyze communication streams
- Reconstruct network sessions
- Extract transferred files
- Investigate suspicious traffic

These operations are essential during SOC investigations and network forensics.

---

## Packet Inspection

Analysts can inspect packet details such as:
- Source and destination IP addresses
- Ports and protocols
- Packet payloads
- TCP flags
- Timing information

Detailed inspection helps identify suspicious network behavior.

---

## Following Streams

Wireshark allows analysts to reconstruct communications using:
- TCP streams
- UDP streams
- HTTP streams

This helps visualize complete conversations between systems.

Examples:
- Reviewing HTTP requests and responses
- Analyzing command-and-control (C2) traffic
- Investigating suspicious communications

---

## Packet Filtering

Display filters help isolate relevant packets quickly.

Examples:

```wireshark
http
```

```wireshark
tcp.stream eq 0
```

```wireshark
dns
```

```wireshark
ip.addr == 10.10.10.5
```

---

## Exporting Objects

Wireshark supports extracting transferred objects such as:
- HTTP files
- Images
- Documents
- Malware samples

This capability is useful during malware analysis and incident investigations.

---

## Network Investigation Workflow

Typical workflow:
- Open packet capture (PCAP)
- Apply filters
- Inspect suspicious packets
- Follow communication streams
- Extract relevant artifacts
- Analyze Indicators of Compromise (IOCs)

---

## Indicators of Suspicious Activity

Examples include:
- Suspicious HTTP requests
- Unusual DNS traffic
- Repeated connections
- Malicious file transfers
- Beaconing communications

---

## Applied protocol filters  and applied advanced filtering 

<img width="1279" height="620" alt="Screenshot 2026-05-12 211653" src="https://github.com/user-attachments/assets/91fb8a7b-1bcd-4389-890e-c2b0ccf667aa" />


---

## Best Practices

Recommended approaches:
- Use filters to reduce noise
- Inspect packet payloads carefully
- Follow suspicious communication streams
- Validate extracted files safely
- Correlate packet data with security alerts

---

## Key Learnings
- Packet operations improve network investigations
- Stream reconstruction helps analyze communications
- Exporting objects supports malware analysis
- Packet filtering speeds up investigations
- Detailed packet inspection reveals suspicious behavior

---

## Screenshot of room completion

<img width="1103" height="485" alt="Screenshot 2026-05-12 211715" src="https://github.com/user-attachments/assets/25a826f4-01f0-4040-8a19-e0a36e8a092d" />

---

## Notes
This room introduced important packet operation features within Wireshark and demonstrated how SOC analysts use packet inspection, stream analysis, and object extraction during network investigations and incident response activities.
