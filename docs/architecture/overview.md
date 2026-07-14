# SOC Lab Architecture

This document explains how the SOC lab is set up and how logs travel from the monitored systems to the Wazuh Dashboard.

---

# Lab Overview

The lab was created using Oracle VirtualBox. A dedicated Ubuntu Server was used as the Wazuh Manager, while Windows and Linux machines acted as monitored endpoints.

The endpoints generate different security events, which are collected by Wazuh agents and sent to the Wazuh Manager for analysis.

---

# Virtual Machines

| Machine | Purpose |
|----------|---------|
| Ubuntu Server | Wazuh Manager, Dashboard and Indexer |
| Windows 11 | Windows endpoint for monitoring and threat simulation |
| Ubuntu Desktop | Linux endpoint for monitoring |
| Kali Linux | Linux endpoint used for testing and attack simulation |

---

# Wazuh Components

## Wazuh Manager

The Wazuh Manager receives logs from all connected agents, analyzes them using built-in detection rules, and generates alerts whenever suspicious activity is detected.

---

## Wazuh Indexer

The Indexer stores alerts and security events so they can be searched from the dashboard.

---

## Wazuh Dashboard

The Dashboard provides a web interface to monitor agents, search logs, investigate alerts, and perform basic threat hunting.

---

## Wazuh Agents

Each monitored machine runs a Wazuh agent. The agent collects logs and forwards them to the Wazuh Manager.

In this project, agents were installed on:

- Windows 11
- Ubuntu Desktop
- Kali Linux

---

# Monitoring Tools

## Sysmon

Sysmon was installed on the Windows machine to generate detailed system activity such as process creation, registry changes, and other endpoint events.

---

## Auditd

Auditd was used on Linux systems to monitor important activities such as user management, file access, and privilege escalation.

---

# Log Flow

The overall log flow in the lab is shown below.

```text
Windows / Linux Endpoint
          │
          ▼
     Wazuh Agent
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
 Alert Investigation
```

---

# Detection Workflow

The following steps describe how an event is detected.

1. An activity is performed on a monitored endpoint.
2. The Wazuh agent collects the generated logs.
3. The logs are sent to the Wazuh Manager.
4. Wazuh analyzes the logs using its detection rules.
5. If a rule matches, an alert is generated.
6. The alert is stored in the Indexer.
7. The alert can be investigated from the Dashboard.

---

# Summary

This architecture helped me understand how a SIEM collects logs, detects suspicious activity, and presents alerts for investigation. It also provided hands-on experience with monitoring both Windows and Linux systems from a single platform.
