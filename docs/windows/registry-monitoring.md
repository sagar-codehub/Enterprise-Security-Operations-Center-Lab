# Windows Registry Monitoring

## Objective

The objective of this test was to monitor Windows Registry changes using Sysmon and verify that Wazuh detects and records these events.

---

# Why is it Important?

The Windows Registry stores important system and application settings. Attackers may modify registry keys to establish persistence, disable security features, or change system configurations.

Monitoring registry changes helps detect unauthorized modifications that could indicate malicious activity.

---

# Environment

| Component | Value |
|----------|---------|
| Operating System | Windows 11 |
| SIEM | Wazuh |
| Endpoint Monitoring | Sysmon |
| Agent | Wazuh Agent |

---

# Steps Performed

### Step 1: Open Registry Editor

Open **Registry Editor (regedit)** with administrative privileges.

---

### Step 2: Modify a Registry Key

Create or modify a registry value for testing purposes.

> **Note:** Perform registry modifications only in a controlled lab environment.

---

### Step 3: Verify the Event

Wait for the event to be processed and search for the generated alert in the Wazuh Dashboard.

---

# Detection

Wazuh successfully detected the registry modification event collected by Sysmon.

The alert included information about the modified registry key, the process responsible for the change, and the affected endpoint.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1112 | Modify Registry |

---

# What I Learned

- Registry changes can be monitored effectively using Sysmon and Wazuh.
- Unauthorized registry modifications may indicate persistence or other malicious activity.
- Monitoring registry events improves visibility into changes made on Windows endpoints.
