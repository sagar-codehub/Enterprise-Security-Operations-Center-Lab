# Threat Hunting

## Overview

Threat hunting is the process of proactively searching for suspicious activities that may indicate malicious behavior. During this project, I used the Wazuh Dashboard to investigate alerts generated from different Windows and Linux detection scenarios.

---

# Hunting Workflow

The following steps were followed for each investigation:

1. Generate a security event on the monitored endpoint.
2. Wait for the event to be processed by Wazuh.
3. Open the Wazuh Dashboard.
4. Search for the generated alert.
5. Review the alert details.
6. Identify the affected endpoint and user.
7. Verify whether the activity was expected or suspicious.

---

# Windows Threat Hunting

The following Windows activities were investigated:

| Activity | Status |
|----------|--------|
| User Creation | Investigated |
| Account Discovery | Investigated |
| Registry Monitoring | Investigated |
| File Integrity Monitoring | Investigated |

For each alert, the following details were reviewed:

- Agent Name
- Rule ID
- Rule Level
- Username
- Event Time
- MITRE ATT&CK Technique

---

# Linux Threat Hunting

The following Linux activities were investigated:

| Activity | Status |
|----------|--------|
| SSH Successful Login | Investigated |
| SSH Failed Login | Investigated |
| Privilege Escalation | Investigated |
| User Creation | Investigated |
| User Deletion | Investigated |
| SSH Configuration Tampering | Investigated |
| Cron Persistence | Investigated |
| Suspicious Process Execution | Investigated |
| Sensitive File Access | Investigated |
| Log Tampering | Investigated |
| Systemd Service Persistence | Investigated |

For each alert, the following details were reviewed:

- Agent Name
- Username
- Rule ID
- Rule Level
- Event Time
- MITRE ATT&CK Technique

---

# Investigation Process

During each investigation, I focused on answering the following questions:

- Which endpoint generated the alert?
- Which user performed the activity?
- When did the event occur?
- What action triggered the alert?
- Which MITRE ATT&CK technique was associated with the event?
- Does the activity appear legitimate or suspicious?

---

# What I Learned

- Threat hunting requires understanding both normal and suspicious system activity.
- Wazuh provides enough information to investigate alerts from both Windows and Linux endpoints.
- Reviewing alert details helps determine whether an event requires further investigation.
