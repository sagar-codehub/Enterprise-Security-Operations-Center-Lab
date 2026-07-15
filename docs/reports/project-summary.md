# Project Summary

## Overview

This project involved building a Security Operations Center (SOC) lab using Wazuh SIEM to monitor Windows and Linux endpoints. The lab was created in Oracle VirtualBox and focused on understanding how security events are collected, analyzed, and investigated.

The project included endpoint monitoring, log collection, threat detection, and basic threat hunting using Wazuh.

---

# Lab Environment

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

---

# Implemented Scenarios

## Windows

- Windows Agent Deployment
- Sysmon Installation
- User Creation Detection
- Account Discovery Detection
- Registry Monitoring
- File Integrity Monitoring

---

## Linux

- Auditd Integration
- SSH Successful Login Detection
- SSH Failed Login Detection
- Privilege Escalation Detection
- User Creation Detection
- User Deletion Detection
- SSH Configuration Tampering
- Cron Persistence Detection
- Suspicious Process Execution Detection
- Sensitive File Access Detection
- Log Tampering Detection
- Systemd Service Persistence Detection

---

# Skills Developed

During this project, I gained practical experience with:

- Wazuh SIEM deployment
- Windows endpoint monitoring
- Linux endpoint monitoring
- Sysmon configuration
- Auditd configuration
- File Integrity Monitoring (FIM)
- Threat Hunting
- Alert Investigation
- MITRE ATT&CK Mapping
- Basic SOC operations

---

# Challenges Faced

Some of the challenges encountered during the project included:

- Wazuh agent connectivity issues
- Auditd configuration
- XML configuration errors
- Oracle VirtualBox networking
- OPNsense log decoding
- Service troubleshooting

Each issue helped improve my understanding of how the different components of a SOC environment work together.

---

# Conclusion

This project helped me understand the workflow of a Security Operations Center by providing hands-on experience with monitoring, detection, investigation, and troubleshooting. It also strengthened my understanding of Windows and Linux security monitoring using Wazuh.
