# Systemd Service Persistence Detection

## Objective

The objective of this test was to verify whether Wazuh can detect the creation or modification of a systemd service on the Ubuntu Desktop.

---

# Why is it Important?

Systemd services are used to manage background processes on Linux systems. Attackers may create or modify services to execute malicious programs automatically whenever the system starts.

Monitoring systemd services helps identify persistence techniques and unauthorized configuration changes.

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

### Step 1: Create a Service File

Create a new systemd service file.

Example:

```bash
sudo nano /etc/systemd/system/test.service
```

---

### Step 2: Configure the Service

Add the required service configuration and save the file.

---

### Step 3: Reload the Systemd Daemon

Reload the systemd manager configuration.

```bash
sudo systemctl daemon-reload
```

---

### Step 4: Enable the Service

Enable the service so it starts automatically during system boot.

```bash
sudo systemctl enable test.service
```

---

### Step 5: Verify the Detection

Open the Wazuh Dashboard and search for the generated event.

Verify that Wazuh successfully detected the creation or modification of the systemd service.

---

# Detection

Wazuh successfully detected the systemd service activity on the Ubuntu Desktop.

The generated alert included information such as:

- Agent name
- Username
- Service file
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1543.002 | Create or Modify System Process: Systemd Service |

---

# What I Learned

- Wazuh can detect changes made to systemd service files.
- Monitoring systemd services helps identify persistence techniques on Linux systems.
- Service creation and modification events should be reviewed during security investigations.
