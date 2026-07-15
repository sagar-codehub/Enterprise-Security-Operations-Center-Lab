# SSH Failed Login Detection

## Objective

The objective of this test was to verify whether Wazuh can detect failed SSH login attempts on the Ubuntu Desktop.

---

# Why is it Important?

Failed SSH login attempts can occur due to incorrect passwords or unauthorized login attempts. Monitoring these events helps identify suspicious authentication activity and possible brute-force attacks.

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

---

### Step 2: Connect from Kali Linux

Open the terminal on Kali Linux and attempt to connect to the Ubuntu Desktop.

```bash
ssh username@<Ubuntu_Desktop_IP>
```

---

### Step 3: Enter an Incorrect Password

When prompted, enter an incorrect password several times.

After multiple failed attempts, the SSH connection will be denied.

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated SSH authentication events.

Verify that Wazuh detected the failed login attempts.

---

# Detection

Wazuh successfully detected the failed SSH login attempts generated on the Ubuntu Desktop.

The generated alert included information such as:

- Agent name
- Username
- Source IP Address
- Authentication failure
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1110 | Brute Force |

---

# What I Learned

- Wazuh can detect failed SSH authentication attempts.
- Repeated failed logins may indicate password guessing or brute-force attacks.
- Monitoring authentication failures helps identify suspicious login activity at an early stage.
