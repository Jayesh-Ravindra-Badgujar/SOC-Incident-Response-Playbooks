
# Linux Authentication Log

## Overview

Linux authentication logs (`/var/log/auth.log`) record security-related events such as user logins, SSH authentication, privilege escalation, and sudo activity. SOC analysts monitor these logs to detect unauthorized access attempts, brute-force attacks, privilege escalation, and suspicious user behavior.

---

# Sample Authentication Logs

## 1. Successful SSH Login

```log
Jul 14 09:12:45 kali sshd[2145]: Accepted password for jayesh from 192.168.1.15 port 54218 ssh2
```

**Analysis**

- User: `jayesh`
- Source IP: `192.168.1.15`
- Authentication: Password
- Status: Successful Login

---

## 2. Failed SSH Login

```log
Jul 14 09:15:22 kali sshd[2190]: Failed password for invalid user admin from 203.0.113.45 port 45221 ssh2
```

**Analysis**

- Invalid username attempted
- External source IP
- Possible brute-force attempt

---

## 3. Multiple Failed Login Attempts

```log
Jul 14 09:16:01 kali sshd[2203]: Failed password for root from 203.0.113.45 port 45235 ssh2
Jul 14 09:16:03 kali sshd[2205]: Failed password for root from 203.0.113.45 port 45240 ssh2
Jul 14 09:16:06 kali sshd[2208]: Failed password for root from 203.0.113.45 port 45246 ssh2
```

**Analysis**

- Repeated authentication failures
- Same source IP
- Possible brute-force attack

---

## 4. Successful Sudo Authentication

```log
Jul 14 09:20:17 kali sudo: jayesh : TTY=pts/0 ; PWD=/home/jayesh ; USER=root ; COMMAND=/usr/bin/apt update
```

**Analysis**

- User executed a privileged command
- Verify whether the activity was authorized

---

## 5. Failed Sudo Authentication

```log
Jul 14 09:21:44 kali sudo: pam_unix(sudo:auth): authentication failure; logname=jayesh uid=1000 euid=0 tty=/dev/pts/0 ruser=jayesh rhost= user=jayesh
```

**Analysis**

- Incorrect sudo password entered
- May indicate user error or unauthorized privilege escalation attempt

---

## 6. User Session Opened

```log
Jul 14 09:22:10 kali systemd-logind[825]: New session 12 of user jayesh.
```

**Analysis**

- User session successfully created
- Useful for session tracking

---

## 7. User Session Closed

```log
Jul 14 10:05:42 kali systemd-logind[825]: Session 12 logged out. Waiting for processes to exit.
```

**Analysis**

- User logged out successfully
- Indicates session termination

---

## 8. SSH Connection Closed

```log
Jul 14 10:05:43 kali sshd[2145]: Disconnected from user jayesh 192.168.1.15 port 54218
```

**Analysis**

- SSH session ended normally

---

# Common Authentication Indicators

SOC analysts should monitor for:

- Multiple failed login attempts
- Successful login after repeated failures
- Root login attempts
- Invalid usernames
- Unauthorized sudo usage
- Login attempts from unknown IP addresses
- Authentication outside business hours
- Repeated SSH connection attempts
- Privilege escalation activity

---

# Investigation Workflow

1. Review authentication logs.
2. Identify source IP addresses.
3. Determine affected users.
4. Check login success after failures.
5. Review sudo activity.
6. Verify privileged access.
7. Correlate events with SIEM alerts.
8. Escalate if unauthorized access is suspected.

---

# MITRE ATT&CK Mapping

| Technique | ID |
|------------|----|
| Brute Force | T1110 |
| Password Guessing | T1110.001 |
| Valid Accounts | T1078 |
| SSH | T1021.004 |
| Sudo and Sudo Caching | T1548.003 |

---

# Log File Location

Ubuntu / Debian / Kali Linux

```bash
/var/log/auth.log
```

RHEL / CentOS / Fedora

```bash
/var/log/secure
```

---

# Useful Commands

View the latest authentication logs:

```bash
sudo tail -50 /var/log/auth.log
```

Search for failed SSH logins:

```bash
grep "Failed password" /var/log/auth.log
```

Search for successful SSH logins:

```bash
grep "Accepted password" /var/log/auth.log
```

Search for sudo activity:

```bash
grep "sudo" /var/log/auth.log
```

View live authentication logs:

```bash
sudo tail -f /var/log/auth.log
```
