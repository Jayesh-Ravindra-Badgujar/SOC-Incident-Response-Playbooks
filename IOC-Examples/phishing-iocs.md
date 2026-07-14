# Phishing Indicators of Compromise (IOCs)

## Overview

This document lists common Indicators of Compromise (IOCs) associated with phishing attacks. These indicators help Security Operations Center (SOC) analysts identify, investigate, and respond to phishing incidents quickly and consistently.

---

# What is an IOC?

An Indicator of Compromise (IOC) is a piece of evidence that suggests a system, user, or network may have been targeted or compromised by a cyber attack.

---

# Email-Based Indicators

- Unknown or unexpected sender
- Spoofed email address
- Misspelled domain name
- Display name impersonation
- Reply-To address different from sender
- Suspicious email subject
- Generic greeting (e.g., "Dear Customer")
- Poor grammar or spelling mistakes
- Urgent requests for action
- Requests for passwords or sensitive information

---

# URL Indicators

Look for:

- Shortened URLs (bit.ly, tinyurl, etc.)
- Misspelled domain names
- Look-alike domains
- IP address instead of domain name
- Multiple URL redirects
- Newly registered domains
- HTTP instead of HTTPS
- Suspicious query parameters

Example:

```
https://micr0soft-support-login.com
```

---

# Attachment Indicators

Common malicious attachment types include:

- .exe
- .bat
- .js
- .vbs
- .scr
- .zip
- .rar
- .iso
- .docm
- .xlsm
- .pptm

Possible behaviors:

- Requests to enable macros
- Password-protected archives
- Unexpected invoices
- Fake shipping documents

---

# User Behavior Indicators

Examples include:

- User clicked a suspicious link
- User downloaded an attachment
- User enabled Office macros
- User entered credentials into a fake login page
- User reported a suspicious email

---

# Endpoint Indicators

Possible signs on an endpoint:

- Unknown process execution
- PowerShell launched from Microsoft Office
- Unexpected scheduled tasks
- New startup entries
- Suspicious registry modifications
- Browser credential theft
- Antivirus detection

---

# Network Indicators

Possible network-related IOCs include:

- DNS requests to unknown domains
- Connections to malicious IP addresses
- Connections to recently registered domains
- Unusual outbound traffic
- HTTP POST requests to suspicious servers
- SSL certificate anomalies

---

# SIEM Detection Sources

Common log sources:

- Wazuh SIEM
- Splunk
- Microsoft Defender
- Email Security Gateway
- Windows Event Logs
- DNS Logs
- Proxy Logs
- Firewall Logs
- Web Server Logs

---

# Common Windows Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4688 | Process Creation |
| 4104 | PowerShell Script Block Logging |
| 5156 | Windows Filtering Platform Connection Allowed |

---

# Recommended Analyst Actions

When phishing IOCs are identified:

1. Validate the alert.
2. Identify affected users.
3. Review email headers.
4. Analyze URLs and attachments.
5. Check endpoint activity.
6. Search SIEM for related events.
7. Contain affected accounts or systems.
8. Escalate if credential compromise or malware execution is confirmed.
9. Document findings and preserve evidence.
