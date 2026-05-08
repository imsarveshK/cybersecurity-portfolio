# Elastic Stack: The Basics

## Objective
Learn the fundamentals of the Elastic Stack (ELK Stack), including data collection, log analysis, visualization, and security monitoring within a SOC environment.

---

## Concepts Covered
- Elastic Stack (ELK Stack)
- Elasticsearch
- Logstash
- Kibana
- Beats
- Log analysis
- Data visualization
- Security monitoring

---

## Elastic Stack Overview

The Elastic Stack is a collection of tools used for:
- Collecting logs and telemetry data
- Processing and indexing data
- Searching and analyzing events
- Visualizing security information

The stack is commonly used by SOC teams for centralized logging and security monitoring.

---

## Components of the Elastic Stack

### Elasticsearch
A search and analytics engine used to:
- Store indexed data
- Perform searches
- Analyze large volumes of logs
## used elastic for basic search-
<img width="1279" height="553" alt="Screenshot 2026-05-08 185056" src="https://github.com/user-attachments/assets/6ad7fc56-43d5-45d5-a076-cd0bbb5e0524" />

---

### Logstash
A data processing pipeline used to:
- Collect logs
- Parse incoming data
- Transform and forward events

---

### Kibana
A visualization platform used to:
- Explore log data
- Create dashboards
- Investigate security events
- Visualize trends and alerts

---

### Beats
Lightweight data shippers used to send logs and telemetry data to Elasticsearch or Logstash.

Examples include:
- Filebeat
- Metricbeat
- Packetbeat
- Winlogbeat

---

## Log Analysis & Investigation

SOC analysts use the Elastic Stack to:
- Search security logs
- Investigate suspicious events
- Monitor infrastructure
- Analyze authentication activity
- Correlate security events

---

## Kibana Dashboards

Kibana provides:
- Interactive dashboards
- Visual analytics
- Search functionality
- Event filtering
- Timeline analysis

These dashboards help analysts identify unusual activity quickly.

---

## Security Monitoring Workflow

Typical workflow:
- Collect logs using Beats
- Process logs through Logstash
- Store and index data in Elasticsearch
- Investigate and visualize data in Kibana

---

## Best Practices

Recommended approaches:
- Monitor logs continuously
- Create meaningful dashboards
- Filter irrelevant events
- Correlate security activity
- Retain logs for investigations

---

## Key Learnings
- The Elastic Stack supports centralized security monitoring
- Elasticsearch enables efficient log searching and analysis
- Kibana dashboards improve visibility into security events
- Logstash processes and transforms incoming data
- Beats simplify log collection from endpoints and systems

---

## Screenshot of room comletion-
<img width="883" height="313" alt="Screenshot 2026-05-08 213406" src="https://github.com/user-attachments/assets/a55712ee-c8ba-45c3-a67e-639d97493ba4" />

---

## Notes
This room introduced the fundamentals of the Elastic Stack and demonstrated how SOC analysts use Elasticsearch, Logstash, Kibana, and Beats for log management, event analysis, and security monitoring.
