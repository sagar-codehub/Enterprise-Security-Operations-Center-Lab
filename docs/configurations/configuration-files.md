# Configuration Files

This document provides an overview of the main configuration files used and modified during the SOC lab.

---

# Wazuh Manager Configuration

**File Location**

```text
/var/ossec/etc/ossec.conf
```

### Purpose

This is the main configuration file for the Wazuh Manager. It controls log collection, agent communication, File Integrity Monitoring, and other monitoring features.

### Configuration Changes

During this project, this file was modified to:

- Configure File Integrity Monitoring (FIM)
- Configure log collection
- Enable required monitoring features
- Support Linux endpoint monitoring

---

# Wazuh Agent Configuration

**Linux**

```text
/var/ossec/etc/ossec.conf
```

**Windows**

```text
C:\Program Files (x86)\ossec-agent\ossec.conf
```

### Purpose

The Wazuh Agent configuration defines how the endpoint communicates with the Wazuh Manager and what information is collected.

### Configuration Changes

- Connected the agent to the Wazuh Manager
- Configured endpoint monitoring
- Verified agent connectivity

---

# Auditd Configuration

**File Location**

```text
/etc/audit/audit.rules
```

### Purpose

Auditd rules define which Linux activities should be monitored.

### Configuration Changes

Rules were added to monitor:

- User management
- SSH configuration changes
- Sensitive file access
- Cron modifications
- Systemd service changes

---

# SSH Configuration

**File Location**

```text
/etc/ssh/sshd_config
```

### Purpose

This file controls the SSH service on Linux systems.

### Configuration Changes

A test modification was performed to verify that Wazuh could detect configuration changes.

---

# Cron Configuration

**User Cron**

```text
crontab -e
```

### Purpose

Cron schedules commands to run automatically.

### Configuration Changes

A test cron job was created to verify Wazuh's ability to detect scheduled task modifications.

---

# Systemd Service

**File Location**

```text
/etc/systemd/system/
```

### Purpose

Systemd manages background services on Linux.

### Configuration Changes

A test service was created to verify whether Wazuh detected systemd service creation and persistence activities.

---

# Sysmon Configuration

**Configuration File**

```text
sysmonconfig.xml
```

### Purpose

The Sysmon configuration determines which Windows events are collected.

### Configuration Changes

Sysmon was installed using a configuration file to collect detailed Windows security events that were forwarded to Wazuh.

---

# Summary

The configuration files used throughout this project were modified only within the lab environment to test different monitoring and detection scenarios. These configurations enabled Wazuh to collect endpoint logs, detect security events, and generate alerts for further investigation.
