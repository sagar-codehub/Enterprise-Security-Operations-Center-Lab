# Log Tampering Detection

## Objective

The objective of this test was to verify whether Wazuh can detect modifications made to Linux log files.

---

# Why is it Important?

System logs are important for security investigations and incident response. Attackers may attempt to modify or delete log files to hide their activities and make detection more difficult.

Monitoring log files helps identify unauthorized changes and possible attempts to cover tracks.

---

# Environment

| Component | Value |
|----------|---------|
| Target Machine | Ubuntu Desktop |
| SIEM | Wazuh |
| Monitoring Tool | Auditd |
| Agent | Wazuh Agent |

---

# Steps Performed

### Step 1: Open the Terminal

Log in to the Ubuntu Desktop and open the terminal.

---

### Step 2: Modify a Log File

For testing purposes, make a small change to a monitored log file.

Example:

```bash
sudo nano /var/log/auth.log
```

Save the file and exit the editor.

> **Note:** This activity was performed only in the lab environment for testing purposes.

---

### Step 3: Verify the Detection

Open the Wazuh Dashboard and search for the generated event.

Verify that Wazuh successfully detected the modification to the monitored log file.

---

# Detection

Wazuh successfully detected the modification of the monitored log file.

The generated alert included information such as:

- Agent name
- Username
- Modified log file
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1070.002 | Indicator Removal on Host: Clear Linux or Mac System Logs |

---

# What I Learned

- Wazuh can detect modifications made to monitored log files.
- Log monitoring helps identify attempts to hide malicious activity.
- Protecting system logs is important for effective incident investigation.
