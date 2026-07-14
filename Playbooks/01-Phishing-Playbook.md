# Phishing Incident Response Playbook

## Overview

This playbook provides a standardized approach for Security Operations Center (SOC) analysts to detect, investigate, contain, eradicate, and recover from phishing incidents. It is designed following the NIST SP 800-61 Incident Response Lifecycle and incorporates MITRE ATT&CK techniques relevant to phishing attacks.

---

# Incident Information

| Field | Value |
|-------|-------|
| Incident Type | Phishing |
| Severity | Medium - High |
| Category | Email Security |
| Analyst | SOC L1 |
| Framework | NIST SP 800-61 |
| MITRE ATT&CK | T1566 |

---

# Objective

- Detect phishing emails at an early stage.
- Prevent credential compromise.
- Minimize business impact.
- Document findings for future analysis.
- Escalate confirmed incidents when required.

---

# Scope

This playbook applies to:

- Suspicious emails
- Credential harvesting attacks
- Malicious attachments
- Malicious URLs
- Business Email Compromise (BEC)
- Spear Phishing attempts

---

# Detection Sources

The following tools and log sources can be used to detect phishing incidents:

- Email Security Gateway
- Microsoft Defender
- Wazuh SIEM
- Splunk
- User Reports
- Antivirus Alerts
- DNS Logs
- Proxy Logs
- Web Browser Logs

---

# Indicators of Compromise (IOCs)

Examples of phishing indicators include:

- Suspicious sender email address
- Misspelled domain names
- URL shorteners
- Unexpected attachments
- Password reset emails not requested
- Urgent financial requests
- Office macros
- Executable attachments
- Suspicious hyperlinks
- Credential harvesting pages

---

# Investigation Procedure

## Step 1 - Validate the Alert

- Confirm the email exists.
- Verify sender information.
- Review email subject.
- Determine affected users.

---

## Step 2 - Analyze Email Header

Check:

- Return Path
- SPF
- DKIM
- DMARC
- Originating IP
- Received Headers

---

## Step 3 - Inspect URLs

- Extract URLs
- Check domain reputation
- Verify HTTPS certificate
- Compare domain spelling
- Analyze redirects

---

## Step 4 - Analyze Attachments

Check file type.

Examples:

- PDF
- DOCM
- XLSM
- ZIP
- ISO
- EXE

Upload suspicious files to a malware sandbox if permitted.

---

## Step 5 - Search for Similar Emails

Use SIEM queries to determine:

- Number of recipients
- Similar sender
- Same subject line
- Same attachment hash

---

## Step 6 - Determine Impact

Identify:

- Number of affected users
- Credentials entered
- Malware executed
- Data accessed
- Privileged accounts involved

---

# Containment

Perform the following actions:

- Quarantine malicious emails.
- Block sender domain.
- Block malicious URLs.
- Isolate affected endpoints if necessary.
- Disable compromised accounts.
- Force password reset.
- Enable MFA if not already configured.

---

# Eradication

- Remove phishing emails.
- Delete malicious attachments.
- Remove malware (if present).
- Block indicators across security tools.
- Update email security policies.

---

# Recovery

- Restore affected systems.
- Verify account integrity.
- Re-enable disabled accounts.
- Monitor for additional phishing activity.
- Inform affected users.

---

# Escalation Criteria

Escalate immediately if:

- Privileged account compromised
- Malware executed
- Multiple users affected
- Data exfiltration suspected
- Business Email Compromise detected
- Lateral movement observed

Escalation Target:

- SOC L2 Analyst
- Incident Response Team
- Security Manager

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|------------|
| Phishing | T1566 |
| Spearphishing Attachment | T1566.001 |
| Spearphishing Link | T1566.002 |
| Spearphishing via Service | T1566.003 |

---

# Lessons Learned

After the incident:

- Update phishing detection rules.
- Improve email filtering policies.
- Conduct user awareness training.
- Update blocklists.
- Document newly observed IOCs.
- Review response timeline.
- Identify process improvements.

---

# References

- NIST SP 800-61 Revision 2
- MITRE ATT&CK Framework
- OWASP Phishing Prevention Guidelines
- Microsoft Security Documentation
- Wazuh Documentation
- Splunk Documentation
