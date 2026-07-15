# Linux Privilege Escalation Detection

## Objective

The objective of this test was to verify whether Wazuh can detect privilege escalation activities performed using the `sudo` command on the Ubuntu Desktop.

---

# Why is it Important?

Privilege escalation is a common technique used by attackers after gaining initial access to a system. Monitoring `sudo` usage helps identify administrative actions and detect unauthorized attempts to gain elevated privileges.

---

# Environment

| Component | Value |
|----------|---------|
| Source Machine | Ubuntu Desktop |
| SIEM | Wazuh |
| Monitoring Tool | Auditd |
| Agent | Wazuh Agent |

---

# Steps Performed

### Step 1: Open the Terminal

Log in to the Ubuntu Desktop and open the terminal.

---

### Step 2: Execute a Command Using sudo

Run any command with elevated privileges.

Example:

```bash
sudo apt update
```

Enter the user's password when prompted.

---

### Step 3: Verify the Command Execution

Confirm that the command executes successfully with administrative privileges.

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated `sudo` event.

Verify that Wazuh has successfully detected the privilege escalation activity.

---

# Detection

Wazuh successfully detected the execution of the `sudo` command on the Ubuntu Desktop.

The generated alert included information such as:

- Agent name
- Username
- Executed command
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1548 | Abuse Elevation Control Mechanism |

---

# What I Learned

- Wazuh can detect commands executed with elevated privileges.
- Monitoring `sudo` usage helps identify administrative activities on Linux systems.
- Unexpected privilege escalation events should always be investigated to verify whether they are legitimate or malicious.
