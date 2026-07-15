# Auditd Integration

## Objective

The objective of this task was to install and configure Auditd on the Ubuntu Desktop so that important system activities could be monitored and forwarded to Wazuh.

---

# Why is it Important?

Auditd is the Linux Audit Daemon that records security-related events such as user management, file access, command execution, and privilege escalation.

Integrating Auditd with Wazuh improves visibility into system activities and helps detect suspicious behavior.

---

# Environment

| Component | Value |
|----------|---------|
| Operating System | Ubuntu Desktop |
| SIEM | Wazuh |
| Monitoring Tool | Auditd |
| Agent | Wazuh Agent |

---

# Steps Performed

### Step 1: Install Auditd

Install Auditd using the package manager.

```bash
sudo apt install auditd audispd-plugins
```

---

### Step 2: Verify the Installation

Check whether the Auditd service is running.

```bash
sudo systemctl status auditd
```

---

### Step 3: Enable the Service

If the service is not running, enable and start it.

```bash
sudo systemctl enable auditd
sudo systemctl start auditd
```

---

### Step 4: Configure Audit Rules

Add the required audit rules to monitor system activities.

After updating the rules, restart the Auditd service.

```bash
sudo systemctl restart auditd
```

---

### Step 5: Verify the Integration

Generate a test event and verify that it appears in the Wazuh Dashboard.

---

# Detection

After integrating Auditd with Wazuh, Linux audit events were successfully collected and displayed in the Wazuh Dashboard.

These events were later used to monitor:

- User creation
- User deletion
- Privilege escalation
- Sensitive file access
- SSH configuration changes
- Other Linux security events

---

# What I Learned

- Auditd provides detailed visibility into Linux system activities.
- Wazuh uses Auditd logs to generate meaningful security alerts.
- Proper Auditd configuration is important for accurate event monitoring.
