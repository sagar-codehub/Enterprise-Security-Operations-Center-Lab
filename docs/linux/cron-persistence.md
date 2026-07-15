# Cron Persistence Detection

## Objective

The objective of this test was to verify whether Wazuh can detect changes made to scheduled cron jobs on the Ubuntu Desktop.

---

# Why is it Important?

Cron is used to schedule tasks on Linux systems. While it is commonly used for system administration, attackers may create cron jobs to execute malicious commands automatically and maintain persistence on the system.

Monitoring cron activity helps detect unauthorized scheduled tasks.

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

### Step 1: Open the User Crontab

Open the crontab editor.

```bash
crontab -e
```

---

### Step 2: Create a Scheduled Task

Add a new cron job for testing purposes.

Example:

```text
* * * * * echo "Cron Test" >> /tmp/cron_test.log
```

Save the file and exit the editor.

---

### Step 3: Verify the Cron Job

Display the configured cron jobs.

```bash
crontab -l
```

---

### Step 4: Verify the Detection

Open the Wazuh Dashboard and search for the generated cron event.

Verify that Wazuh successfully detected the creation or modification of the cron job.

---

# Detection

Wazuh successfully detected the cron job modification performed on the Ubuntu Desktop.

The generated alert included information such as:

- Agent name
- Username
- Modified cron configuration
- Event timestamp

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1053.003 | Scheduled Task/Job: Cron |

---

# What I Learned

- Wazuh can detect changes made to cron jobs.
- Monitoring scheduled tasks helps identify persistence techniques.
- Unexpected cron entries should always be reviewed during an investigation.
