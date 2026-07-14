# Brute Force Login Incident Response Playbook

## Overview

This playbook provides a standardized approach for Security Operations Center (SOC) analysts to detect, investigate, contain, eradicate, and recover from brute-force login attacks. It follows the NIST SP 800-61 Incident Response Lifecycle and maps relevant adversary techniques to the MITRE ATT&CK framework.

---

# Incident Information

| Field | Value |
|-------|-------|
| Incident Type | Brute Force Login Attack |
| Severity | Medium - High |
| Category | Authentication Security |
| Analyst | SOC L1 |
| Framework | NIST SP 800-61 |
| MITRE ATT&CK | T1110 |

---

# Objective

- Detect unauthorized authentication attempts.
- Identify compromised or targeted accounts.
- Prevent unauthorized access.
- Minimize business impact.
- Escalate confirmed attacks when necessary.

---

# Scope

This playbook applies to:

- Windows authentication attacks
- Linux SSH brute-force attacks
- RDP login attacks
- VPN authentication attacks
- Web application login attacks
- Password spraying attacks

---

# Detection Sources

The following tools and log sources can be used to detect brute-force attacks:

- Wazuh SIEM
- Splunk
- Windows Event Viewer
- Linux Authentication Logs (/var/log/auth.log)
- Active Directory Logs
- VPN Logs
- Firewall Logs
- IDS/IPS Alerts
- Microsoft Defender

---

# Indicators of Compromise (IOCs)

Examples of brute-force attack indicators include:

- Multiple failed login attempts
- Event ID 4625 (Failed Logon)
- Repeated SSH authentication failures
- Password spraying attempts
- Account lockouts
- Multiple login attempts from the same IP address
- Authentication attempts against multiple user accounts
- Unusual login times
- Logins from unfamiliar geographic locations
- Excessive authentication failures in a short period

---

# Investigation Procedure

## Step 1 - Validate the Alert

- Confirm the authentication alert.
- Identify the affected account.
- Verify alert severity.
- Determine the authentication source.

---

## Step 2 - Collect Initial Information

Gather the following:

- Username
- Source IP Address
- Destination System
- Hostname
- Timestamp
- Authentication Method

---

## Step 3 - Analyze Authentication Logs

Review:

- Windows Security Logs
- Linux auth.log
- VPN authentication logs
- RDP logs
- Active Directory logs

Look for:

- Number of failed logins
- Successful login after failures
- Account lockout events
- Multiple targeted accounts
- Login frequency

---

## Step 4 - Analyze Source Information

Identify:

- Source IP reputation
- Geographical location
- Internal or external source
- Multiple destination systems
- Previous malicious activity

---

## Step 5 - Determine Impact

Identify:

- Number of affected accounts
- Privileged accounts targeted
- Successful authentication
- Account compromise
- Lateral movement attempts
- Business systems affected

---

# Containment

Perform the following actions:

- Block the malicious IP address.
- Lock or disable compromised accounts.
- Force password reset for affected users.
- Enable Multi-Factor Authentication (MFA) if not already enabled.
- Increase authentication monitoring.
- Preserve relevant authentication logs.

---

# Eradication

- Remove malicious IP addresses from allowlists.
- Block attacker infrastructure.
- Review password policies.
- Disable unused accounts.
- Update firewall and IDS/IPS rules.
- Remove unauthorized user accounts if discovered.

---

# Recovery

- Restore affected user accounts.
- Verify successful password changes.
- Monitor authentication logs for recurring attempts.
- Confirm normal user access.
- Review account security settings.
- Continue monitoring for suspicious login activity.

---

# Escalation Criteria

Escalate immediately if:

- Administrative or privileged accounts are targeted.
- Successful account compromise is confirmed.
- Multiple systems are affected.
- Password spraying is detected.
- Lateral movement is suspected.
- Business-critical systems are impacted.

Escalation Target:

- SOC L2 Analyst
- Incident Response Team
- Identity and Access Management (IAM) Team
- Security Manager

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|------------|
| Brute Force | T1110 |
| Password Guessing | T1110.001 |
| Password Cracking | T1110.002 |
| Password Spraying | T1110.003 |
| Credential Stuffing | T1110.004 |

---

# Lessons Learned

After the incident:

- Review password complexity policies.
- Enforce Multi-Factor Authentication (MFA).
- Implement account lockout policies.
- Block malicious IP addresses.
- Improve authentication monitoring rules.
- Update SIEM detection rules.
- Conduct user awareness training on password security.
- Document newly observed Indicators of Compromise (IOCs).
- Review the incident response timeline for process improvements.

---

# References

- NIST SP 800-61 Revision 2
- MITRE ATT&CK Framework
