# SSH Successful Login Detection

## Objective

The objective of this test was to verify whether Wazuh can detect a successful SSH login on the Ubuntu Desktop from another machine in the lab.

---

# Why is it Important?

SSH is widely used for remote administration of Linux systems. Monitoring successful SSH logins helps track user activity and identify unauthorized remote access.

---

# Environment

| Component | Value |
|----------|---------|
| Source Machine | Kali Linux |
| Target Machine | Ubuntu Desktop |
| SIEM | Wazuh |
| Monitoring Tool | Auditd |
| Agent | Wazuh Agent |

---

# Steps Performed

### Step 1: Verify the SSH Service

On the Ubuntu Desktop, verify that the SSH service is running.

```bash
sudo systemctl status ssh
```

If the service is not running, start it using:

```bash
sudo systemctl start ssh
```

---

### Step 2: Connect from Kali Linux

Open the terminal on Kali Linux and connect to the Ubuntu Desktop using SSH.

```bash
ssh username@<Ubuntu_Desktop_IP>
```

Replace:

- `username` with your Ubuntu Desktop username.
- `<Ubuntu_Desktop_IP>` with the IP address of the Ubuntu Desktop.

---

### Step 3: Authenticate

Enter the correct password to establish the SSH session successfully.

Once authenticated, you will gain remote access to the Ubuntu Desktop.

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated SSH login event.

Verify that Wazuh has successfully detected the login activity from the Ubuntu Desktop agent.

---

# Detection

Wazuh successfully detected the successful SSH login event generated on the Ubuntu Desktop.

The alert included information such as:

- Agent name
- Username
- Source IP Address
- Authentication status
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1078 | Valid Accounts |

---

# What I Learned

- Wazuh can successfully detect SSH login events on Linux systems.
- Successful SSH logins provide useful information during security investigations.
- Monitoring remote logins helps identify unusual or unauthorized access attempts.
