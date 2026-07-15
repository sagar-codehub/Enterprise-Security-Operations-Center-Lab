# MITRE ATT&CK Mapping

This document maps the detection scenarios implemented in this project to the corresponding MITRE ATT&CK techniques.

> **Note:** The mappings are based on the activities performed during this lab and are intended for learning purposes.

---

# Windows

| Detection Scenario | MITRE Technique | Technique ID |
|--------------------|-----------------|--------------|
| Windows User Creation Detection | Create Account: Local Account | T1136.001 |
| Windows Account Discovery | Account Discovery: Local Account | T1087.001 |
| Windows Registry Monitoring | Modify Registry | T1112 |
| Windows File Integrity Monitoring | File Deletion | T1070.004 |

---

# Linux

| Detection Scenario | MITRE Technique | Technique ID |
|--------------------|-----------------|--------------|
| SSH Successful Login | Valid Accounts | T1078 |
| SSH Failed Login | Brute Force | T1110 |
| Privilege Escalation | Abuse Elevation Control Mechanism | T1548 |
| Linux User Creation | Create Account: Local Account | T1136.001 |
| Linux User Deletion | Account Access Removal | T1531 |
| SSH Configuration Tampering | Impair Defenses | T1562 |
| Cron Persistence | Scheduled Task/Job: Cron | T1053.003 |
| Suspicious Process Execution | Command and Scripting Interpreter | T1059 |
| Sensitive File Access | OS Credential Dumping | T1003 |
| Log Tampering | Indicator Removal on Host: Clear Linux or Mac System Logs | T1070.002 |
| Systemd Service Persistence | Create or Modify System Process: Systemd Service | T1543.002 |

---

# Summary

This project covers multiple stages of the MITRE ATT&CK framework, including:

- Initial Access
- Persistence
- Privilege Escalation
- Defense Evasion
- Discovery
- Credential Access
- Execution

The implemented scenarios demonstrate how Wazuh can monitor and detect activities associated with these techniques across both Windows and Linux systems.
