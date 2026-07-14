# Enterprise Security Operations Center (SOC) Lab

A hands-on Security Operations Center (SOC) lab built using **Wazuh SIEM** to monitor and investigate security events across Windows and Linux systems.

The purpose of this project was to understand how logs are collected, how security events are detected, and how analysts investigate alerts in a SOC environment. The lab includes multiple virtual machines, endpoint monitoring, threat simulations, file integrity monitoring, and MITRE ATT&CK mapping.

> **Note:** This project was built for learning and practical experience. All attack scenarios and detections were performed in an isolated virtual lab.

---

## Project Objectives

- Build a working SOC lab using Wazuh SIEM.
- Deploy and manage Windows and Linux agents.
- Monitor endpoint activities using Sysmon and Auditd.
- Generate and investigate security events.
- Perform basic threat hunting using Wazuh Dashboard.
- Understand how different attack techniques appear in SIEM logs.
- Map detections to the MITRE ATT&CK framework.

---

## Lab Environment

| Component | Technology |
|----------|------------|
| Virtualization | Oracle VirtualBox |
| SIEM | Wazuh |
| Wazuh Manager | Ubuntu Server |
| Dashboard | Wazuh Dashboard |
| Indexer | Wazuh Indexer |
| Windows Endpoint | Windows 11 |
| Linux Endpoints | Ubuntu Desktop, Kali Linux |
| Windows Monitoring | Sysmon |
| Linux Monitoring | Auditd |
| Threat Mapping | MITRE ATT&CK |

---

## Features

- Windows and Linux endpoint monitoring
- Centralized log collection using Wazuh
- Sysmon event monitoring
- Auditd integration
- File Integrity Monitoring (FIM)
- SSH activity monitoring
- Privilege escalation detection
- User account monitoring
- Registry monitoring
- Cron persistence detection
- Systemd service persistence detection
- Threat hunting using Wazuh Dashboard
- MITRE ATT&CK mapping

---

## Detection Scenarios

### Windows

- Windows Agent Deployment
- Sysmon Installation
- User Creation Detection
- Account Discovery Detection
- Registry Monitoring
- File Integrity Monitoring

### Linux

- SSH Successful Login
- SSH Failed Login
- Privilege Escalation (sudo)
- User Creation Detection
- User Deletion Detection
- Auditd Integration
- SSH Configuration Tampering
- Cron Persistence
- Suspicious Process Execution
- Sensitive File Access
- Log Tampering
- Systemd Service Persistence


---

## Technologies Used

- Wazuh
- Ubuntu Server
- Ubuntu Desktop
- Windows 11
- Kali Linux
- Oracle VirtualBox
- Sysmon
- Auditd
- Linux
- PowerShell
- Bash
- MITRE ATT&CK

---

## Project Workflow

```text
Endpoints
     │
     ▼
Wazuh Agents
     │
     ▼
Wazuh Manager
     │
     ▼
Wazuh Indexer
     │
     ▼
Wazuh Dashboard
     │
     ▼
Alert Analysis & Threat Hunting
```

---

## Documentation

Project documentation is organized into separate sections:

- Architecture
- Windows Monitoring
- Linux Monitoring
- Auditd
- Sysmon
- File Integrity Monitoring
- Threat Hunting
- MITRE ATT&CK Mapping
- Investigation Reports
- Commands Reference
- Configuration Files
- Troubleshooting Guide

---

## Learning Outcomes

Through this project, I learned how to:

- Deploy and manage Wazuh agents
- Monitor Windows and Linux endpoints
- Analyze security logs
- Investigate alerts in Wazuh Dashboard
- Understand endpoint telemetry
- Perform basic threat hunting
- Relate security events to MITRE ATT&CK techniques
- Troubleshoot common SIEM deployment issues

---

## References

- Wazuh Documentation
- MITRE ATT&CK Framework
- Sysmon Documentation
- Linux Audit Framework (Auditd)

---

## License

This project is licensed under the MIT License.

---

## Acknowledgements

Thanks to the Wazuh community and the open-source cybersecurity community for providing excellent documentation and learning resources that helped during this project.
