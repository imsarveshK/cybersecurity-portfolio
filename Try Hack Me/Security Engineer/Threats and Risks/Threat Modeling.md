# Threat Modeling

## Objective
Understand the fundamentals of threat modeling and learn how organizations identify, analyze, and mitigate potential security threats during system and application design.

---

## Concepts Covered
- Threat modeling
- Threat identification
- Attack surfaces
- Security architecture
- Risk analysis
- STRIDE model
- PASTA model

---

## Threat Modeling Overview

Threat modeling is a structured process used to identify:
- Potential threats
- Security weaknesses
- Attack vectors
- Risks within systems and applications

The goal is to proactively improve security by identifying threats before attackers exploit them.

---

## Importance of Threat Modeling

Threat modeling helps organizations:
- Reduce security risks early
- Improve secure system design
- Identify attack surfaces
- Prioritize security controls
- Strengthen defensive strategies

---

## Threat Modeling Process

Typical threat modeling steps include:

### 1. Define the System
Understand:
- System architecture
- Components
- Data flows
- Trust boundaries

---

### 2. Identify Assets
Identify critical assets requiring protection.

Examples:
- User credentials
- Databases
- Sensitive data
- APIs
- Internal systems

---

### 3. Identify Threats
Analyze potential threats targeting the system.

Examples:
- Spoofing
- Data tampering
- Privilege escalation
- Information disclosure

---

### 4. Assess Risks
Evaluate:
- Likelihood of attacks
- Potential business impact
- Severity of threats

---

### 5. Implement Mitigations
Apply defensive controls to reduce identified risks.

Examples:
- Authentication controls
- Encryption
- Access restrictions
- Input validation

---

## STRIDE Threat Model

The room introduced the STRIDE framework used to classify threats.

### Spoofing
Pretending to be another user or system.

### Tampering
Unauthorized modification of data or systems.

### Repudiation
Performing actions without accountability or traceability.

### Information Disclosure
Unauthorized exposure of sensitive information.

### Denial of Service (DoS)
Disrupting system availability or services.

### Elevation of Privilege
Gaining unauthorized higher-level access.

## Simulated STRIDE threat modeling exercise

<img width="711" height="592" alt="Screenshot 2026-05-21 170253" src="https://github.com/user-attachments/assets/b4adff23-9587-44a9-8fa6-5c74b8bf60c0" />

---

## PASTA Threat Model

The room also introduced the PASTA (Process for Attack Simulation and Threat Analysis) framework, a risk-centric threat modeling methodology focused on attacker behavior and business impact.

### Seven Stages of PASTA

1. Define Business Objectives  
2. Define Technical Scope  
3. Application Decomposition  
4. Threat Analysis  
5. Weakness & Vulnerability Analysis  
6. Attack Modeling & Simulation  
7. Risk & Impact Analysis

## Simulated PASTA threat modeling exercise

<img width="711" height="592" alt="Screenshot 2026-05-21 170253" src="https://github.com/user-attachments/assets/70f2aca2-17f1-4d02-8fc3-35c9d356349b" />

---

## Attack Surfaces

An attack surface includes all possible points attackers may target.

Examples:
- Web applications
- APIs
- Authentication systems
- Open network services

Reducing attack surface improves security posture.

---

## Security Concepts Mentioned

```text
Threat Modeling
STRIDE
PASTA
Attack Surfaces
Risk Assessment
Security Architecture
Data Flow Analysis
Secure Design
```

---

## Best Practices

Recommended approaches:
- Perform threat modeling early in development
- Identify trust boundaries clearly
- Reduce unnecessary attack surfaces
- Validate inputs securely
- Review threats continuously as systems evolve

---

## Key Learnings
- Threat modeling helps identify risks proactively
- STRIDE provides a structured threat classification framework
- PASTA focuses on attacker-centric risk analysis
- Understanding attack surfaces improves defensive planning
- Security should be integrated during system design
- Early risk identification reduces future security issues

---

## Screenshot of room completion

<img width="922" height="393" alt="Screenshot 2026-05-21 175045" src="https://github.com/user-attachments/assets/006d684b-5599-4c64-9eb7-d6e6d6d12400" />

---

## Notes
This room introduced the fundamentals of threat modeling and demonstrated how organizations identify, assess, and mitigate security threats using frameworks such as STRIDE and PASTA to improve secure system design and reduce cybersecurity risks.
