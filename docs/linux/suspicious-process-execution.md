# Suspicious Process Execution Detection

## Objective

The objective of this test was to verify whether Wazuh can detect the execution of a monitored process on the Ubuntu Desktop.

---

# Why is it Important?

Attackers often execute commands or programs after gaining access to a system. Monitoring process execution helps identify unusual or unauthorized activities that may indicate malicious behavior.

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

### Step 2: Execute a Process

Run a command that is monitored by Auditd.

Example:

```bash
whoami
```

You can also test with other commands that are included in your Auditd rules.

---

### Step 3: Verify the Command Execution

Confirm that the command executes successfully.

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated event.

Verify that Wazuh successfully detected the process execution.

---

# Detection

Wazuh successfully detected the monitored process execution on the Ubuntu Desktop.

The generated alert included information such as:

- Agent name
- Username
- Executed command
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1059 | Command and Scripting Interpreter |

---

# What I Learned

- Wazuh can detect monitored process execution on Linux systems.
- Process monitoring provides better visibility into user activities.
- Reviewing executed commands helps identify suspicious behavior during investigations.
