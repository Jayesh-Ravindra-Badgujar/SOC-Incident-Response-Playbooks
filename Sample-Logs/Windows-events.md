
# Windows Security Events

## Overview

Windows Event Logs provide valuable information for detecting, investigating, and responding to security incidents. Security Operations Center (SOC) analysts monitor these logs to identify suspicious activities such as unauthorized logins, privilege escalation, process execution, PowerShell activity, and system changes.

This document summarizes commonly observed Windows Security Event IDs relevant to SOC investigations.

---

# Authentication Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 4624 | Successful Logon | Verify successful user authentication |
| 4625 | Failed Logon | Detect brute-force or password spraying attacks |
| 4634 | User Logoff | Track user session activity |
| 4648 | Logon Using Explicit Credentials | Detect credential misuse |
| 4672 | Special Privileges Assigned | Monitor administrative logins |
| 4740 | User Account Locked Out | Identify brute-force attacks |

---

# Process Creation Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 4688 | Process Creation | Detect suspicious process execution |
| 4689 | Process Termination | Investigate process lifecycle |

Examples:

- cmd.exe
- powershell.exe
- certutil.exe
- mshta.exe
- rundll32.exe
- regsvr32.exe

---

# PowerShell Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 4103 | Module Logging | Monitor PowerShell module execution |
| 4104 | Script Block Logging | Detect malicious PowerShell commands |

Common indicators include:

- Encoded commands
- Download cradle activity
- Base64 encoded scripts
- PowerShell obfuscation

---

# Scheduled Task Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 4698 | Scheduled Task Created | Detect persistence mechanisms |
| 4699 | Scheduled Task Deleted | Investigate cleanup activity |

---

# Service Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 7045 | New Service Installed | Detect malware persistence or unauthorized services |

---

# Firewall Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 5156 | Network Connection Allowed | Investigate outbound and inbound connections |
| 5157 | Network Connection Blocked | Verify firewall enforcement |

---

# Audit Events

| Event ID | Description | SOC Use Case |
|----------|-------------|--------------|
| 1102 | Security Audit Log Cleared | Possible anti-forensics activity |

---

# Common Investigation Workflow

When investigating Windows security events:

1. Validate the security alert.
2. Identify the affected user or system.
3. Review authentication events.
4. Examine process creation logs.
5. Analyze PowerShell activity.
6. Investigate scheduled tasks and services.
7. Correlate logs with SIEM alerts.
8. Determine the scope and impact.
9. Escalate if malicious activity is confirmed.

---

# Example Detection Scenarios

| Event ID | Possible Threat |
|----------|-----------------|
| 4625 | Brute Force Attack |
| 4688 | Malware Execution |
| 4104 | Malicious PowerShell |
| 7045 | Malware Persistence |
| 4698 | Scheduled Task Persistence |
| 1102 | Log Tampering |
| 5156 | Suspicious Network Connection |

---
