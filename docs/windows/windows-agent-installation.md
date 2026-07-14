# Windows Agent Deployment

## Objective

The first step was to connect a Windows machine to the Wazuh Manager so that it could send security logs for monitoring and analysis.

---

# Why Install the Wazuh Agent?

The Wazuh agent collects security-related events from the endpoint and securely sends them to the Wazuh Manager.

Without the agent, the Windows machine cannot be monitored by Wazuh.

---

# Environment

| Component | Value |
|----------|---------|
| Operating System | Windows 11 |
| Monitoring Tool | Wazuh Agent |
| Manager | Ubuntu Server (Wazuh Manager) |

---

# Installation Steps

### 1. Download the Wazuh Agent

Download the Windows agent from the official Wazuh website.

---

### 2. Install the Agent

Run the installer and provide the required information:

- Wazuh Manager IP Address
- Agent Name
- Registration Key (if required)

Complete the installation using the default options.

---

### 3. Start the Agent

After installation, start the Wazuh service from Windows Services or using the command line.

---

### 4. Verify the Connection

From the Wazuh Dashboard, confirm that the Windows endpoint appears as an active agent.

A successful connection indicates that the endpoint is ready to send logs to the manager.

---

# What Was Verified?

After deployment, I verified that:

- The Windows agent successfully connected to the Wazuh Manager.
- The agent status changed to **Active**.
- The endpoint started sending logs to the dashboard.

---

# Outcome

The Windows machine was successfully added to the SOC lab and became available for monitoring. This allowed me to perform the remaining Windows detection scenarios, including Sysmon monitoring, user account monitoring, registry monitoring, and File Integrity Monitoring.

---

# Lessons Learned

- Every monitored endpoint must have a running Wazuh agent.
- A successful agent connection is the foundation for all detections.
- Verifying the agent status before testing detections helps avoid troubleshooting later.
