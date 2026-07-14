# Sysmon Installation

## Objective

After deploying the Windows agent, the next step was to install Sysmon. It provides detailed endpoint logs that help monitor process creation, network connections, registry changes, and other system activities.

---

# Why Sysmon?

Windows Event Viewer records basic system events, but Sysmon extends this by generating more detailed logs that are useful for security monitoring and threat hunting.

These logs are collected by the Wazuh agent and forwarded to the Wazuh Manager for analysis.

---

# Environment

| Component | Value |
|----------|---------|
| Operating System | Windows 11 |
| Monitoring Tool | Sysmon |
| Log Collection | Wazuh Agent |

---

# Installation Steps

### 1. Download Sysmon

Download Sysmon from Microsoft's Sysinternals Suite.

---

### 2. Extract the Files

Extract the downloaded ZIP file to a convenient location.

---

### 3. Install Sysmon

Open Command Prompt or PowerShell as Administrator and install Sysmon using a configuration file.

Example:

```powershell
Sysmon64.exe -accepteula -i sysmonconfig.xml
```

---

### 4. Verify Installation

After installation, verify that the **Sysmon** service is running.

You can also check Windows Event Viewer under:

```
Applications and Services Logs
    └── Microsoft
          └── Windows
                └── Sysmon
                      └── Operational
```

If events start appearing, Sysmon has been installed successfully.

---

# What Was Verified?

After installing Sysmon, I verified that:

- The Sysmon service was running.
- Windows started generating Sysmon events.
- The Wazuh agent successfully collected these events.
- The events were visible in the Wazuh Dashboard.

---

# Why Sysmon Was Important in This Project

Sysmon played an important role in the Windows monitoring scenarios completed during this project, including:

- User account monitoring
- Process monitoring
- Registry monitoring
- File Integrity Monitoring
- Threat hunting using Windows event logs

---

# Lessons Learned

- Sysmon provides much more detailed endpoint visibility than default Windows logs.
- Correct configuration is important because it decides which events are recorded.
- Combining Sysmon with Wazuh makes Windows monitoring much more effective.
