# Splunk: The Basics

## Objective
Learn the fundamentals of Splunk, including searching logs, analyzing events, using SPL queries, and investigating security-related data within a SIEM environment.

---

## Concepts Covered
- Splunk fundamentals
- SIEM investigations
- Log analysis
- SPL (Search Processing Language)
- Event searching
- Security monitoring

---

## Splunk Overview

Splunk is a Security Information and Event Management (SIEM) platform used to:
- Collect and index logs
- Search security events
- Monitor infrastructure
- Investigate suspicious activity
- Generate alerts and dashboards

Splunk helps SOC analysts analyze large volumes of security data efficiently.

---

## Splunk Components

### Forwarder
Used to collect and send log data from endpoints and systems to the Splunk server.

### Indexer
Processes and stores incoming log data for searching and analysis.

### Search Head
Provides the interface used by analysts to:
- Search logs
- Run SPL queries
- Create dashboards
- Investigate incidents

---

## SPL (Search Processing Language)

Splunk uses SPL to search and analyze indexed data.

Example searches:

```spl
index=main
```

```spl
index=main sourcetype=windows
```

---

## Searching & Filtering Events

SOC analysts use Splunk to:
- Search logs
- Filter events
- Identify suspicious activity
- Correlate security events

Common filters include:
- IP addresses
- Usernames
- Event IDs
- Keywords

---

## Event Investigation

Typical investigation workflow:
- Review alerts
- Search related logs
- Analyze event details
- Identify Indicators of Compromise (IOCs)
- Escalate confirmed threats

---

## Common Splunk Capabilities

Splunk features include:
- Centralized log analysis
- Real-time monitoring
- Dashboard visualization
- Alerting
- Event correlation
- Threat investigation

---

## Best Practices

Recommended approaches:
- Use precise search filters
- Correlate related events
- Investigate suspicious activity promptly
- Tune searches to reduce false positives
- Document investigation findings

---

## Key Learnings
- Splunk centralizes security log analysis
- SPL enables efficient event searching
- Analysts use Splunk for alert investigations
- Log correlation improves threat detection
- Effective searching helps identify suspicious behavior quickly

---
## During this exercise, I explored the Splunk Enterprise dashboard and became familiar with the SIEM interface, including:
- Search functionality
- Event investigation panels
- Log filtering
- Timeline visualization
- Field analysis
<img width="764" height="553" alt="Screenshot 2026-05-08 172354" src="https://github.com/user-attachments/assets/9fe70a80-0a1a-4ae6-9731-c1e52b2a977d" />
---

## Screenshot of room completion-
<img width="1279" height="659" alt="Screenshot 2026-05-08 172412" src="https://github.com/user-attachments/assets/425ba938-4016-4d8a-90be-ca9f6bd1607f" />


---

## Notes
This room introduced the basics of Splunk and demonstrated how SOC analysts use SPL queries, log analysis, and event investigation techniques within a SIEM environment.
