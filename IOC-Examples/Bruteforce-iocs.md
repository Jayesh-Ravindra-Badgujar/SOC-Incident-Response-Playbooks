# Brute Force Login Indicators of Compromise (IOCs)

## Overview

This document lists common Indicators of Compromise (IOCs) associated with brute-force login attacks. These indicators help Security Operations Center (SOC) analysts identify, investigate, and respond to authentication-based attacks before unauthorized access is achieved.

---

# What is an IOC?

An Indicator of Compromise (IOC) is a piece of evidence that indicates an attempted or successful security compromise. For brute-force attacks, IOCs primarily originate from authentication logs, network traffic, and endpoint activity.

---

# Authentication Indicators

Common authentication-related indicators include:

- Multiple failed login attempts
- Account lockout events
- Repeated authentication failures from the same IP address
- Login attempts against multiple user accounts
- Successful login following numerous failed attempts
- Authentication attempts outside normal business hours
- Logins from unusual geographic locations
- Repeated password reset requests
- Excessive authentication attempts within a short period

---

# Host-Based Indicators

Possible endpoint indicators include:

- New user sessions immediately after repeated failed logins
- Unauthorized privilege escalation
- Unexpected Remote Desktop (RDP) sessions
- Suspicious SSH sessions
- Administrative account usage outside normal hours
- Multiple user profile access attempts
- Unauthorized account modifications

---

# Network Indicators

Possible network-related indicators include:

- High volume of authentication requests
- Multiple login attempts from a single IP address
- Login attempts from blacklisted IP addresses
- Repeated VPN authentication failures
- SSH connection attempts from external sources
- RDP connection attempts from unknown systems
- Password spraying against multiple accounts
- Authentication requests across multiple servers

---

# Windows Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4634 | Logoff |
| 4648 | Logon Using Explicit Credentials |
| 4672 | Special Privileges Assigned to New Logon |
| 4740 | User Account Locked Out |
| 4768 | Kerberos Authentication Ticket (TGT) Requested |
| 4769 | Kerberos Service Ticket Requested |
| 4771 | Kerberos Pre-Authentication Failed |
| 4776 | NTLM Authentication Attempt |

---

# Linux Indicators

Examples include:

- Multiple failed SSH login attempts
- Invalid username attempts
- Repeated password authentication failures
- Root login attempts
- SSH authentication from unknown IP addresses
- Frequent authentication failures in `/var/log/auth.log`
- Successful SSH login after multiple failures
- Excessive `sudo` authentication failures

---

# SIEM Detection Sources

Common log sources include:

- Wazuh SIEM
- Splunk
- Windows Security Logs
- Linux Authentication Logs
- Active Directory Logs
- VPN Logs
- Firewall Logs
- IDS/IPS Alerts
- Microsoft Defender
- Endpoint Detection & Response (EDR)

---

# Recommended Analyst Actions

When brute-force IOCs are identified:

1. Validate the security alert.
2. Identify the targeted user account(s).
3. Determine the source IP address.
4. Review authentication logs.
5. Check for successful logins following failed attempts.
6. Block malicious IP addresses if required.
7. Lock or disable compromised accounts.
8. Force password reset for affected users.
9. Verify Multi-Factor Authentication (MFA) status.
10. Escalate if account compromise is confirmed.
11. Document findings and preserve relevant logs.

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|------------|
| Brute Force | T1110 |
| Password Guessing | T1110.001 |
| Password Cracking | T1110.002 |
| Password Spraying | T1110.003 |
| Credential Stuffing | T1110.004 |
| Valid Accounts | T1078 |

