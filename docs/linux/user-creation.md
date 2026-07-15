# Linux User Creation Detection

## Objective

The objective of this test was to verify whether Wazuh can detect the creation of a new user account on the Ubuntu Desktop.

---

# Why is it Important?

Creating a new user account is a normal administrative task, but attackers may also create unauthorized accounts to maintain persistent access to a compromised system.

Monitoring user creation events helps identify suspicious account management activities.

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

### Step 2: Create a New User

Create a new user using the following command:

```bash
sudo useradd socuser
```

Verify that the user has been created successfully.

---

### Step 3: Verify the User

Run the following command to confirm the new user exists.

```bash
cat /etc/passwd
```

Alternatively, you can use:

```bash
id socuser
```

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated user creation event.

Verify that Wazuh successfully detected the creation of the new user account.

---

# Detection

Wazuh successfully detected the creation of the new Linux user account.

The generated alert included information such as:

- Agent name
- Username
- Executed command
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1136.001 | Create Account: Local Account |

---

# What I Learned

- Wazuh can detect Linux user account creation events.
- User account creation should be monitored because attackers may create new accounts to maintain access.
- Monitoring account management activities improves visibility into changes made on Linux systems.
