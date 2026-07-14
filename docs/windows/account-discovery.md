# Windows Account Discovery Detection

## Objective

The objective of this test was to verify whether Wazuh can detect account discovery activities performed on a Windows endpoint.

---

# Why is it Important?

Attackers often gather information about user accounts after gaining access to a system. This helps them understand the environment, identify privileged accounts, and plan their next steps.

Monitoring account discovery activities can help identify suspicious reconnaissance behavior.

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

### Step 1: Open Command Prompt

Launch Command Prompt with administrative privileges.

---

### Step 2: List Local User Accounts

Run the following command:

```cmd
net user
```

This command displays all local user accounts available on the system.

---

### Step 3: Observe the Wazuh Dashboard

After executing the command, wait for the event to be processed.

Search for the generated event in the Wazuh Dashboard to verify that the activity was captured.

---

# Detection

Wazuh successfully detected the account discovery activity and generated an alert for the executed command.

The event confirmed that Windows account enumeration activities were being monitored correctly.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1087.001 | Account Discovery: Local Account |

---

# What I Learned

- Account discovery is one of the first activities attackers perform after gaining access to a system.
- Monitoring user enumeration commands helps identify reconnaissance attempts.
- Wazuh can detect these activities and generate alerts for further investigation.
