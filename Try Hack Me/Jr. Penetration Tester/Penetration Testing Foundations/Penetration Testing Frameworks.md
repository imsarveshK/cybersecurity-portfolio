# Lab Logbook: Penetration Testing Frameworks
**Path:** TryHackMe -> Junior Penetration Tester -> Penetration Testing Foundations

## 🎯 Operational Compliance Objective
To analyze the core structured frameworks governing commercial offensive security operations, evaluate the procedural phases of industry-standard testing methodologies, and understand how to map technical exploitation data to regulatory compliance, adversarial behavior matrixes, and risk management models.

## ⚙️ Core Methodologies Evaluated 
- **OSSTMM:** Open Source Security Testing Methodology Manual (Focus: Operational security metrics).
- **OWASP WSTG:** Web Security Testing Guide (Focus: Specialized web application auditing).
- **NIST SP 800-115:** Technical Guide to Information Security Testing (Focus: Government & enterprise testing baselines).
- **PTES:** Penetration Testing Execution Standard (Focus: End-to-end commercial consulting lifecycle).
- **ISSAF:** Information Systems Security Assessment Framework (Focus: Granular, technical testing steps).
- **MITRE ATT&CK:** Adversarial Tactics, Techniques, and Common Knowledge (Focus: Real-world adversary behavior mapping).

---

## 🔍 Technical Analysis & Methodology Breakdown

A successful penetration test requires strict adherence to an established framework to ensure complete asset coverage, legal protection, and repeatable outcomes.

```text
[Pre-engagement / RoE] ──> [OSINT & Intel] ──> [Vulnerability Analysis] ──> [Exploitation] ──> [Post-Exploitation] ──> [MITRE TTP Mapping] ──> [Reporting]
```
### 1. OSSTMM 
Developed by ISECOM, OSSTMM focuses on scientific, quantifiable metrics for operational security.

It evaluates security through operational controls divided into key channels: Human, Physical, Wireless, Telecommunications, and Data Networks.

Rather than providing a basic checklist, it delivers a mathematical approach to measure security presence, minimizing subjective interpretation during enterprise risk evaluations.

### 2. OWASP WSTG 
The Web Security Testing Guide (WSTG) is the premier framework for assessing the security posture of web-based applications, backend services, and APIs.

It outlines continuous validation routines for tracking application layer risks, including improper input mapping, broken session states, cryptographic vulnerabilities, and access control bypasses.

Implementing WSTG workflows ensures compliance with software security best practices during active application deployment.

### 3. NIST SP 800-115 
A highly structured guideline provided by the U.S. National Institute of Standards and Technology for information security testing and assessments.

NIST structures testing activities into four distinct blocks: Target Identification and Analysis, Target Vulnerability Analysis, Vulnerability Flaw Exploitation, and Assessment Reporting.

This framework is widely utilized across federal spaces, financial networks, and heavily regulated corporate environments to ensure absolute adherence to structural baseline compliance.

### 4. PTES 
A highly practical, commercial-grade standard designed to outline the end-to-end consulting lifecycle across seven primary phases:

Pre-engagement Interactions & RoE: Defining strict scoping boundaries, time frames, and emergency white-hat escalation procedures.

Intelligence Gathering: Leveraging open-source intelligence (OSINT) to map out infrastructure boundaries.

Threat Modeling & Vulnerability Analysis: Identifying active weaknesses relative to the target's business threat profile.

Exploitation & Post-Exploitation: Safely penetrating boundaries and identifying the direct business impact of data exposure.

Reporting: Delivering highly detailed executive summaries for management alongside step-by-step technical reproduction playbooks for developers.

### 5. ISSAF 
The Information Systems Security Assessment Framework (ISSAF) organizes testing into highly granular, technical phases.

It is structured explicitly around Evaluation Fields, mapping out exact technical guidelines for evaluating networks, operating systems, databases, and application code layers.

ISSAF's primary value lies in its exhaustive configuration-level testing requirements, serving as an exceptional baseline for detailed infrastructure verification.

### 6. MITRE ATT&CK 
A globally accessible knowledge base of adversary tactics, techniques, and procedures (TTPs) drawn from real-world cyber attack case studies.

It maps the adversarial journey from initial access through execution, defense evasion, lateral movement, and final target exfiltration.

Purple Team Alignment: Pentesters utilize MITRE ATT&CK to simulate realistic, threat-informed attack behaviors, while SOC Analysts use the matrix to ensure corresponding SIEM detection rules are active for each technique.

### 7. Other Notable Frameworks 
Depending on specific sector compliance requirements, offensive operations may pivot to alternative standards, such as:

PCI-DSS Scoping: Specialized frameworks targeting environments processing credit card transactions.

FedRAMP / Cloud-Specific Standards: Frameworks modified to evaluate microservices, APIs, and cloud infrastructure isolation boundaries.

### 🛠️ Engineering, Compliance & Selection Takeaways 
Choosing the Right Framework: A Security Engineer or Tester must select a framework based on target architecture and compliance goals. Web apps demand OWASP WSTG; federal networks require NIST SP 800-115; comprehensive threat-emulation exercises utilize MITRE ATT&CK.

Scoping Controls & Law: Operating outside of the explicit boundary constraints agreed upon in pre-engagement documentation instantly transforms an authorized network assessment into an unauthorized intrusion incident. Enforce rigid rules of engagement.
