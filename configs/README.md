# Configuration Files

This directory contains the configuration files used throughout the Enterprise Security Operations Center (SOC) Lab.

These files were used to configure monitoring, log collection, and endpoint visibility across the Windows and Linux systems.

## Directory Structure

```text
configs/
├── wazuh/
├── auditd/
├── sysmon/
└── ssh/
```

## Wazuh

Contains the Wazuh Manager and Agent configuration files used during the project.

## Auditd

Contains the Auditd rules used to monitor Linux security events.

## Sysmon

Contains the Sysmon configuration used for Windows event collection.

## SSH

Contains the SSH configuration file used for testing SSH configuration monitoring.

> **Note:** These configuration files are intended for educational and lab purposes. Review and modify them before using them in a production environment.
