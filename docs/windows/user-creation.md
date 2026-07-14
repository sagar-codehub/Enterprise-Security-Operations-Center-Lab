# Windows User Creation Detection

## Objective

The objective of this test was to verify whether Wazuh can detect the creation of a new user account on a Windows system.

---

# Why is it Important?

Creating new user accounts is a common administrative task. However, attackers may also create unauthorized accounts to maintain access to a compromised system.

Monitoring account creation helps identify suspicious activity and supports early detection of potential persistence techniques.

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

### Step 1: Create a New User

A new local Windows user account was created using Command Prompt.

```cmd
net user testuser Password@123 /add
```

---

### Step 2: Verify User Creation

The newly created account was verified using:

```cmd
net user
```

The command displayed the list of local user accounts, including the newly created user.

---

### Step 3: Check Wazuh Dashboard

After a few moments, the generated event appeared in the Wazuh Dashboard.

The alert contained information such as:

- Agent name
- Event time
- User account created
- Windows event details

---

# Detection

Wazuh successfully detected the creation of the new Windows user account after the event was generated on the endpoint.

The alert confirmed that user account activities were being monitored correctly.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1136 | Create Account |

---

# What I Learned

- Wazuh can monitor user account creation events on Windows.
- Account creation events provide useful information during security investigations.
- Monitoring administrative actions is important because attackers may create new accounts to maintain access.
