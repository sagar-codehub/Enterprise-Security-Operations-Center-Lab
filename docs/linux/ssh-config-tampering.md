# SSH Configuration Tampering Detection

## Objective

The objective of this test was to verify whether Wazuh can detect changes made to the SSH configuration file on the Ubuntu Desktop.

---

# Why is it Important?

The SSH configuration file controls how remote access is managed on a Linux system. Attackers may modify this file to weaken security settings, enable unauthorized access, or maintain persistence.

Monitoring changes to the SSH configuration helps identify unauthorized modifications.

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

### Step 1: Open the SSH Configuration File

Open the SSH configuration file using a text editor.

```bash
sudo nano /etc/ssh/sshd_config
```

---

### Step 2: Modify the Configuration

Make a small configuration change for testing purposes.

Save the file and exit the editor.

---

### Step 3: Restart the SSH Service

Apply the configuration changes by restarting the SSH service.

```bash
sudo systemctl restart ssh
```

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated event.

Verify that Wazuh successfully detected the modification to the SSH configuration file.

---

# Detection

Wazuh successfully detected the modification of the SSH configuration file.

The generated alert included information such as:

- Agent name
- Modified file
- Username
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1562 | Impair Defenses |

---

# What I Learned

- Wazuh can detect changes made to important Linux configuration files.
- Monitoring SSH configuration files helps identify unauthorized system modifications.
- Configuration file monitoring improves visibility into administrative changes on Linux systems.
