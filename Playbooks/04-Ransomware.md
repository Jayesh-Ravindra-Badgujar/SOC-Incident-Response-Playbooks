# Ransomware Incident Response Playbook

## Overview

This playbook provides a standardized approach for Security Operations Center (SOC) analysts to detect, investigate, contain, eradicate, and recover from ransomware incidents. It follows the NIST SP 800-61 Incident Response Lifecycle and maps attacker behavior using the MITRE ATT&CK framework.

---

# Incident Information

| Field | Value |
|-------|-------|
| Incident Type | Ransomware Attack |
| Severity | Critical |
| Category | Endpoint Security |
| Analyst | SOC L1 |
| Framework | NIST SP 800-61 |
| MITRE ATT&CK | Multiple Techniques |

---

# Objective

- Detect ransomware activity at the earliest possible stage.
- Prevent ransomware from spreading across the environment.
- Preserve forensic evidence.
- Minimize business disruption.
- Escalate critical incidents immediately.

---

# Scope

This playbook applies to:

- File encryption attacks
- Crypto-ransomware
- Locker ransomware
- Network share encryption
- Double-extortion ransomware
- Ransom note detection
- Data exfiltration associated with ransomware

---

# Detection Sources

The following tools and log sources can be used to detect ransomware activity:

- Wazuh SIEM
- Splunk
- Microsoft Defender
- CrowdStrike Falcon
- Windows Event Viewer
- Sysmon
- File Integrity Monitoring (FIM)
- Endpoint Detection & Response (EDR)
- Firewall Logs
- DNS Logs
- Network Traffic Logs

---

# Indicators of Compromise (IOCs)

Examples of ransomware indicators include:

- Large number of files being encrypted
- Unusual file extensions
- Presence of ransom notes
- High disk read/write activity
- Mass file modification events
- Shadow Copy deletion
- Suspicious PowerShell execution
- Unexpected encryption processes
- Connections to malicious Command and Control (C2) servers
- Unauthorized privilege escalation

---

# Investigation Procedure

## Step 1 - Validate the Alert

- Confirm ransomware detection.
- Identify the affected endpoint.
- Verify alert severity.
- Determine whether encryption is active.

---

## Step 2 - Collect Initial Information

Gather the following:

- Hostname
- Username
- IP Address
- Detection Time
- Operating System
- Ransomware family (if identified)

---

## Step 3 - Analyze Endpoint Activity

Review:

- Running processes
- Parent-child process relationships
- Recently created files
- File modification events
- Registry changes
- Scheduled tasks
- Network connections
- Persistence mechanisms

---

## Step 4 - Analyze Security Logs

Review logs from:

- Windows Event Viewer
- Sysmon
- Wazuh Dashboard
- Splunk
- EDR Console
- Firewall Logs

Look for:

- Suspicious process execution
- PowerShell activity
- Privilege escalation
- Lateral movement
- File encryption events
- Network communication

---

## Step 5 - Determine Impact

Identify:

- Number of affected systems
- Critical servers impacted
- Shared drives affected
- Data exfiltration indicators
- Privileged accounts compromised
- Business services disrupted

---

# Containment

Perform the following actions:

- Immediately isolate infected endpoints.
- Disconnect affected systems from the network.
- Disable network shares if necessary.
- Block malicious IP addresses and domains.
- Disable compromised accounts.
- Preserve forensic evidence before making changes.

---

# Eradication

- Remove ransomware binaries.
- Delete malicious scheduled tasks.
- Remove persistence mechanisms.
- Apply security patches.
- Update antivirus and EDR signatures.
- Remove unauthorized services and startup entries.

---

# Recovery

- Restore systems from verified backups.
- Validate system integrity.
- Verify malware removal.
- Reconnect systems after security validation.
- Monitor for reinfection.
- Confirm normal business operations.

---

# Escalation Criteria

Escalate immediately if:

- Multiple endpoints are encrypted.
- Critical business systems are affected.
- Domain Controllers are impacted.
- Data exfiltration is suspected.
- Ransom demand is received.
- Lateral movement is confirmed.
- Backup systems are compromised.

Escalation Target:

- SOC L2 Analyst
- Incident Response Team
- Digital Forensics Team
- Security Manager
- IT Operations Team
- Executive Management (if required)

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|------------|
| Data Encrypted for Impact | T1486 |
| Command and Scripting Interpreter | T1059 |
| Ingress Tool Transfer | T1105 |
| Registry Run Keys / Startup Folder | T1547 |
| Scheduled Task/Job | T1053 |
| PowerShell | T1059.001 |
| Remote Services | T1021 |

---

# Lessons Learned

After the incident:

- Review backup and recovery procedures.
- Improve endpoint detection rules.
- Enable File Integrity Monitoring (FIM).
- Patch vulnerable systems.
- Strengthen access control policies.
- Conduct ransomware awareness training.
- Update Indicators of Compromise (IOCs).
- Improve SIEM detection rules.
- Review incident response timeline and identify process improvements.

---

# References

- NIST SP 800-61 Revision 2
- MITRE ATT&CK Framework
