# Sensitive File Access Detection

## Objective

The objective of this test was to verify whether Wazuh can detect access to sensitive files on the Ubuntu Desktop.

---

# Why is it Important?

Sensitive files contain important system and user information. Attackers often access these files to gather credentials, user details, or system configuration information after gaining access to a machine.

Monitoring access to these files helps detect suspicious post-compromise activities.

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

### Step 2: Access a Sensitive File

Read the contents of a monitored file.

Example:

```bash
sudo cat /etc/passwd
```

If `/etc/shadow` was configured for monitoring, you can also test using:

```bash
sudo cat /etc/shadow
```

---

### Step 3: Verify File Access

Confirm that the command executes successfully.

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated event.

Verify that Wazuh successfully detected the file access activity.

---

# Detection

Wazuh successfully detected access to the monitored sensitive file.

The generated alert included information such as:

- Agent name
- Username
- Accessed file
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1003 | OS Credential Dumping |

---

# What I Learned

- Wazuh can detect access to monitored sensitive files.
- Monitoring important system files helps identify suspicious user activity.
- Sensitive file access events provide valuable information during security investigations.
