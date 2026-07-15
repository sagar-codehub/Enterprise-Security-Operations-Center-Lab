# SOC Investigation Reports

## Overview

This document summarizes the investigation process followed for the alerts generated during the SOC lab. Each alert was reviewed in the Wazuh Dashboard to understand what happened, identify the affected system, and determine whether the activity was expected or suspicious.

---

# Investigation Workflow

The following steps were followed during each investigation:

1. Generate a security event.
2. Wait for the alert to appear in the Wazuh Dashboard.
3. Open the alert details.
4. Review the event information.
5. Identify the affected endpoint.
6. Verify the MITRE ATT&CK technique.
7. Determine whether the activity was expected or required further investigation.

---

# Windows Investigations

## User Creation Detection

**Activity:** Created a new local Windows user.

**Investigation:**

- Verified the affected Windows endpoint.
- Reviewed the generated alert.
- Confirmed the username involved.
- Verified the associated MITRE ATT&CK technique.

**Result:**

The activity matched the expected user creation performed during testing.

---

## Account Discovery

**Activity:** Executed the `net user` command.

**Investigation:**

- Verified the command execution.
- Reviewed the generated alert.
- Confirmed that the activity was detected successfully.

**Result:**

The alert matched the expected account discovery activity.

---

## Registry Monitoring

**Activity:** Modified a Windows Registry key.

**Investigation:**

- Verified the affected registry path.
- Reviewed the generated alert.
- Confirmed that the registry modification was successfully detected.

**Result:**

The alert accurately reflected the registry change performed during testing.

---

## File Integrity Monitoring

**Activity:** Created, modified, and deleted files inside a monitored directory.

**Investigation:**

- Verified the monitored file path.
- Reviewed the generated alerts.
- Confirmed that each file operation was detected.

**Result:**

File creation, modification, and deletion events were successfully monitored.

---

# Linux Investigations

## SSH Successful Login

**Activity:** Connected from Kali Linux to the Ubuntu Desktop using SSH.

**Investigation:**

- Verified the Ubuntu Desktop agent.
- Reviewed the generated SSH authentication alert.
- Confirmed the username and source IP address.
- Verified the associated MITRE ATT&CK technique.

**Result:**

The successful SSH login was detected and recorded correctly.

---

## SSH Failed Login

**Activity:** Attempted to log in from Kali Linux using an incorrect password.

**Investigation:**

- Reviewed the failed authentication alert.
- Verified the username and source IP address.
- Confirmed multiple failed login attempts.
- Checked the associated MITRE ATT&CK technique.

**Result:**

The failed SSH login attempts were detected successfully.

---

## Privilege Escalation

**Activity:** Executed a command using `sudo`.

**Investigation:**

- Reviewed the generated alert.
- Verified the user who executed the command.
- Confirmed that the event was associated with privilege escalation.
- Checked the corresponding MITRE ATT&CK technique.

**Result:**

The privilege escalation activity was successfully detected.

---

## User Creation

**Activity:** Created the `socuser` account.

**Investigation:**

- Reviewed the generated user creation alert.
- Verified the username of the newly created account.
- Confirmed that the activity matched the performed test.

**Result:**

The user creation event was detected successfully.

---

## User Deletion

**Activity:** Deleted the `socuser` account.

**Investigation:**

- Reviewed the generated user deletion alert.
- Verified the deleted username.
- Confirmed that the alert matched the performed action.

**Result:**

The account deletion event was detected successfully.

---

## SSH Configuration Tampering

**Activity:** Modified the SSH configuration file.

**Investigation:**

- Reviewed the generated alert.
- Verified the modified configuration file.
- Confirmed that the file change was detected correctly.

**Result:**

The SSH configuration modification was detected successfully.

---

## Cron Persistence

**Activity:** Created a cron job for testing.

**Investigation:**

- Reviewed the generated cron-related alert.
- Verified the user responsible for the change.
- Confirmed that the scheduled task was detected.

**Result:**

The cron job creation was detected successfully.

---

## Suspicious Process Execution

**Activity:** Executed a monitored command.

**Investigation:**

- Reviewed the generated process execution alert.
- Verified the executed command.
- Confirmed the user responsible for the activity.

**Result:**

The monitored process execution was detected successfully.

---

## Sensitive File Access

**Activity:** Accessed a monitored sensitive file.

**Investigation:**

- Reviewed the generated alert.
- Verified the accessed file.
- Confirmed the user responsible for the file access.

**Result:**

The sensitive file access activity was detected successfully.

---

## Log Tampering

**Activity:** Modified a monitored log file.

**Investigation:**

- Reviewed the generated alert.
- Verified the modified log file.
- Confirmed that the event matched the performed action.

**Result:**

The log file modification was detected successfully.

---

## Systemd Service Persistence

**Activity:** Created a new systemd service.

**Investigation:**

- Reviewed the generated alert.
- Verified the created service.
- Confirmed that the service creation activity was captured.

**Result:**

The systemd service creation was detected successfully.

---

# Summary

All planned detection scenarios were successfully tested in the SOC lab. The generated alerts were reviewed in the Wazuh Dashboard to understand how security events are collected, analyzed, and investigated across Windows and Linux systems.
