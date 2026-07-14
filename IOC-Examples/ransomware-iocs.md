# Ransomware Indicators of Compromise (IOCs)

## Overview

This document lists common Indicators of Compromise (IOCs) associated with ransomware attacks. These indicators help Security Operations Center (SOC) analysts detect, investigate, contain, and respond to ransomware incidents before they spread across the environment.

---

# What is an IOC?

An Indicator of Compromise (IOC) is a piece of evidence that suggests a system or network has been compromised. In ransomware incidents, IOCs are commonly observed through endpoint behavior, file system activity, authentication logs, network traffic, and security monitoring tools.

---

# Host-Based Indicators

Common endpoint indicators include:

- Sudden encryption of multiple files
- Appearance of ransom notes (e.g., README.txt, DECRYPT_FILES.txt)
- Unknown or suspicious processes consuming high CPU resources
- Rapid file renaming or extension changes
- Unauthorized deletion of Shadow Copies
- Unexpected system slowdowns
- Disabled antivirus or security software
- Unauthorized registry modifications
- Creation of suspicious scheduled tasks
- Unexpected Windows services

---

# File-Based Indicators

Common file-related indicators include:

- Files encrypted with unknown extensions
- Presence of ransom note files
- Multiple files modified within a short time
- Encrypted documents, images, and databases
- Executable files in temporary directories
- Suspicious DLL files
- Batch scripts (.bat)
- PowerShell scripts (.ps1)
- Visual Basic scripts (.vbs)
- JavaScript files (.js)

---

# Process Indicators

Possible malicious process behavior includes:

- PowerShell execution with encoded commands
- Command Prompt launched by Office applications
- Suspicious parent-child process relationships
- Execution from AppData or Temp directories
- High disk read/write activity
- File encryption processes
- Unexpected privilege escalation
- Process injection attempts
- Unknown background services

---

# Persistence Indicators

Common persistence mechanisms include:

- Registry Run Keys
- Startup Folder entries
- Scheduled Tasks
- Windows Services
- WMI Event Subscriptions
- Startup scripts
- New local administrator accounts
- Browser persistence extensions

---

# Network Indicators

Possible network-related indicators include:

- Connections to Command and Control (C2) servers
- DNS requests to suspicious domains
- High-volume outbound network traffic
- SMB traffic between endpoints
- Lateral movement attempts
- Connections over uncommon ports
- Communication with known malicious IP addresses
- Remote Desktop Protocol (RDP) activity from unknown hosts
- Unexpected data uploads (possible exfiltration)

---

# Windows Event IDs

| Event ID | Description |
|----------|-------------|
| 4688 | Process Creation |
| 4689 | Process Termination |
| 4104 | PowerShell Script Block Logging |
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4672 | Special Privileges Assigned to New Logon |
| 4698 | Scheduled Task Created |
| 7045 | New Service Installed |
| 1102 | Security Audit Log Cleared |
| 5156 | Windows Filtering Platform Connection Allowed |

---

# Linux Indicators

Examples include:

- Unauthorized privilege escalation
- Unknown cron jobs
- Suspicious shell scripts
- Unexpected file encryption
- Changes to critical configuration files
- New user account creation
- Unauthorized SSH access
- Reverse shell activity
- Unexpected outbound network connections

---

# SIEM Detection Sources

Common log sources include:

- Wazuh SIEM
- Splunk
- Microsoft Defender
- CrowdStrike Falcon
- Windows Event Viewer
- Sysmon
- Linux Authentication Logs
- File Integrity Monitoring (FIM)
- Firewall Logs
- DNS Logs
- Proxy Logs
- EDR Alerts

---

# Recommended Analyst Actions

When ransomware IOCs are identified:

1. Validate the security alert.
2. Identify affected systems and users.
3. Immediately isolate infected endpoints.
4. Preserve forensic evidence before making changes.
5. Review running processes and active network connections.
6. Analyze endpoint and SIEM logs.
7. Block malicious IP addresses and domains.
8. Disable compromised accounts if necessary.
9. Verify backup availability.
10. Escalate immediately if encryption is confirmed.
11. Document findings and preserve Indicators of Compromise (IOCs).

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|------------|
| Data Encrypted for Impact | T1486 |
| Command and Scripting Interpreter | T1059 |
| PowerShell | T1059.001 |
| Ingress Tool Transfer | T1105 |
| Registry Run Keys / Startup Folder | T1547 |
| Scheduled Task/Job | T1053 |
| Remote Services | T1021 |
| Valid Accounts | T1078 |
