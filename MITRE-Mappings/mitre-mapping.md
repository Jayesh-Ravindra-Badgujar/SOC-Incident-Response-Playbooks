# MITRE ATT&CK Mapping

## Overview

This document maps the incident response playbooks in this repository to the MITRE ATT&CK® framework. The mapping helps Security Operations Center (SOC) analysts understand the tactics and techniques adversaries commonly use during cyber attacks.

The MITRE ATT&CK framework is a globally recognized knowledge base that categorizes adversary behavior based on real-world observations. Mapping incidents to ATT&CK techniques enables analysts to improve threat detection, investigation, incident response, and defensive strategies.

---

# MITRE ATT&CK Matrix

| Incident Type | Technique | Technique ID | MITRE Tactic |
|---------------|-----------|--------------|--------------|
| Phishing | Phishing | T1566 | Initial Access |
| Phishing | Spearphishing Attachment | T1566.001 | Initial Access |
| Phishing | Spearphishing Link | T1566.002 | Initial Access |
| Phishing | Spearphishing via Service | T1566.003 | Initial Access |
| Brute Force Login | Brute Force | T1110 | Credential Access |
| Brute Force Login | Password Guessing | T1110.001 | Credential Access |
| Brute Force Login | Password Cracking | T1110.002 | Credential Access |
| Brute Force Login | Password Spraying | T1110.003 | Credential Access |
| Brute Force Login | Credential Stuffing | T1110.004 | Credential Access |
| Brute Force Login | Valid Accounts | T1078 | Defense Evasion |
| Ransomware | Data Encrypted for Impact | T1486 | Impact |
| Ransomware | Command and Scripting Interpreter | T1059 | Execution |
| Ransomware | PowerShell | T1059.001 | Execution |
| Ransomware | Ingress Tool Transfer | T1105 | Command and Control |
| Ransomware | Registry Run Keys / Startup Folder | T1547 | Persistence |
| Ransomware | Scheduled Task/Job | T1053 | Persistence |
| Ransomware | Remote Services | T1021 | Lateral Movement |
| Ransomware | Valid Accounts | T1078 | Defense Evasion |

---

# MITRE ATT&CK Tactics Covered

This repository covers techniques from the following MITRE ATT&CK tactics:

- Initial Access
- Execution
- Persistence
- Privilege Escalation
- Defense Evasion
- Credential Access
- Discovery
- Lateral Movement
- Command and Control
- Impact

---

# Incident-to-Technique Mapping

## Phishing

**Primary Goal:** Gain initial access through social engineering.

### Common Techniques

| Technique | ID |
|-----------|----|
| Phishing | T1566 |
| Spearphishing Attachment | T1566.001 |
| Spearphishing Link | T1566.002 |
| Spearphishing via Service | T1566.003 |

---

## Brute Force Login

**Primary Goal:** Obtain valid credentials through repeated authentication attempts.

### Common Techniques

| Technique | ID |
|-----------|----|
| Brute Force | T1110 |
| Password Guessing | T1110.001 |
| Password Cracking | T1110.002 |
| Password Spraying | T1110.003 |
| Credential Stuffing | T1110.004 |
| Valid Accounts | T1078 |

---

## Ransomware

**Primary Goal:** Encrypt files and disrupt business operations.

### Common Techniques

| Technique | ID |
|-----------|----|
| Data Encrypted for Impact | T1486 |
| PowerShell | T1059.001 |
| Registry Run Keys / Startup Folder | T1547 |
| Scheduled Task/Job | T1053 |
| Remote Services | T1021 |
| Ingress Tool Transfer | T1105 |

---

# SOC Analyst Usage

SOC analysts can use this mapping to:

- Identify attacker behavior during investigations.
- Correlate SIEM alerts with ATT&CK techniques.
- Prioritize incident response activities.
- Improve detection rules.
- Enhance threat hunting.
- Standardize security investigations.

---

# Integration with This Repository

| Directory | Purpose |
|-----------|---------|
| Playbooks/ | Incident response procedures |
| IOC-Examples/ | Indicators of Compromise |
| MITRE-Mappings/ | ATT&CK technique mappings |
| Flowcharts/ | Investigation workflows |
| Sample-Logs/ | Example security events |
| Incident-Templates/ | Incident reporting templates |
