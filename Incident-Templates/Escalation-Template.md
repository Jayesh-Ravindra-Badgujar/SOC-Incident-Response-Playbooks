# Security Incident Escalation Template

## Overview

This template is used by Security Operations Center (SOC) analysts to escalate confirmed or high-priority security incidents to higher-level analysts (SOC L2/L3), the Incident Response (IR) team, or Security Management. It ensures that all relevant information is communicated consistently and efficiently.

---

# Escalation Information

| Field | Details |
|--------|---------|
| Escalation ID | INC-YYYY-XXXX |
| Escalation Date | YYYY-MM-DD |
| Escalation Time | HH:MM UTC |
| Escalated By | SOC L1 Analyst |
| Escalated To | SOC L2 / Incident Response Team |
| Priority | Critical / High / Medium / Low |
| Incident Status | Open / Under Investigation / Contained |

---

# Incident Summary

**Incident Type**

> Example: Phishing, Malware Infection, Brute Force Login, Ransomware

**Incident Description**

Provide a brief summary of the incident, including how it was detected and why escalation is required.

---

# Detection Information

| Field | Details |
|--------|---------|
| Detection Source | Wazuh / Splunk / EDR / Firewall / IDS |
| Alert Name | Example Alert |
| Alert Severity | Low / Medium / High / Critical |
| Detection Time | YYYY-MM-DD HH:MM |
| MITRE ATT&CK Technique | Example: T1566 |

---

# Affected Assets

| Asset | Details |
|--------|---------|
| Hostname | |
| IP Address | |
| Operating System | |
| Username | |
| Department | |
| Critical Asset | Yes / No |

---

# Indicators of Compromise (IOCs)

Include all relevant IOCs identified during the investigation.

Examples:

- Malicious IP Address
- Malicious Domain
- Suspicious URL
- File Hash (SHA256)
- Suspicious Process
- Registry Key
- File Path
- Email Address

---

# Investigation Summary

Document the investigation performed.

Examples:

- Reviewed SIEM alerts
- Analyzed Windows Event Logs
- Checked authentication logs
- Investigated PowerShell activity
- Reviewed endpoint telemetry
- Validated Indicators of Compromise (IOCs)

---

# Actions Performed

Record all actions taken before escalation.

Examples:

- Validated alert
- Collected evidence
- Isolated endpoint
- Disabled compromised account
- Blocked malicious IP
- Blocked malicious domain
- Reset user password
- Preserved forensic evidence

---

# Reason for Escalation

Select the reason(s) for escalation.

- Critical asset affected
- Privileged account compromised
- Malware execution confirmed
- Ransomware activity detected
- Data exfiltration suspected
- Multiple systems affected
- Lateral movement detected
- Business impact identified
- Additional investigation required

---

# Evidence Collected

Attach or reference collected evidence.

Examples:

- SIEM screenshots
- Event Viewer logs
- Sysmon logs
- Authentication logs
- Firewall logs
- Network captures
- Malware hash values
- Timeline of events

---

# Recommended Next Actions

Suggested actions for the receiving team.

Examples:

- Perform forensic analysis
- Conduct malware analysis
- Hunt for additional Indicators of Compromise
- Review affected systems
- Monitor for lateral movement
- Verify backup integrity
- Restore affected services
- Continue containment

---

# Escalation Checklist

| Task | Status |
|------|--------|
| Alert validated | ☐ |
| Incident severity assigned | ☐ |
| Evidence collected | ☐ |
| IOCs documented | ☐ |
| Affected assets identified | ☐ |
| Containment actions completed | ☐ |
| Timeline documented | ☐ |
| Incident documented | ☐ |
| Escalation completed | ☐ |

---

# Escalation Timeline

| Time | Activity |
|------|----------|
| HH:MM | Alert received |
| HH:MM | Investigation started |
| HH:MM | Initial analysis completed |
| HH:MM | Containment initiated |
| HH:MM | Escalated to SOC L2 / IR Team |

---
