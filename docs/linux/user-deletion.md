# Linux User Deletion Detection

## Objective

The objective of this test was to verify whether Wazuh can detect the deletion of a user account on the Ubuntu Desktop.

---

# Why is it Important?

Deleting user accounts is a common administrative task. However, attackers may also remove accounts to hide their activities or disrupt legitimate user access.

Monitoring user deletion events helps identify unauthorized account management activities.

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

### Step 2: Delete the User

Delete the previously created user using the following command.

```bash
sudo userdel socuser
```

---

### Step 3: Verify the User Deletion

Run the following command to confirm that the user has been removed.

```bash
id socuser
```

If the deletion is successful, the system will return a message indicating that the user does not exist.

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated user deletion event.

Verify that Wazuh successfully detected the deletion of the user account.

---

# Detection

Wazuh successfully detected the deletion of the Linux user account.

The generated alert included information such as:

- Agent name
- Username
- Deleted account
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1531 | Account Access Removal |

---

# What I Learned

- Wazuh can detect Linux user deletion events.
- Monitoring account deletion helps identify unauthorized administrative actions.
- User management events provide valuable information during security investigations.
