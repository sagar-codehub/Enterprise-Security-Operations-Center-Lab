# Windows File Integrity Monitoring

## Objective

The objective of this test was to verify whether Wazuh can detect file changes on a Windows system using File Integrity Monitoring (FIM).

---

# Why is it Important?

File Integrity Monitoring helps identify changes made to important files and directories. Unexpected file creation, modification, or deletion may indicate unauthorized activity or an attempted attack.

Monitoring file changes improves visibility into endpoint activity and helps detect suspicious behavior.

---

# Environment

| Component | Value |
|----------|---------|
| Operating System | Windows 11 |
| SIEM | Wazuh |
| Monitoring Feature | File Integrity Monitoring (FIM) |
| Agent | Wazuh Agent |

---

# Steps Performed

### Step 1: Configure File Integrity Monitoring

Configure Wazuh to monitor the required Windows directory.

---

### Step 2: Generate File Events

Perform different file operations inside the monitored directory.

- Create a new file
- Modify an existing file
- Delete a file

---

### Step 3: Verify the Events

Open the Wazuh Dashboard and search for the generated file integrity events.

Verify that each file operation is successfully detected.

---

# Detection

Wazuh successfully detected the monitored file changes.

The generated alerts contained information about:

- File name
- File path
- Event type
- Timestamp
- Monitored endpoint

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1070.004 | File Deletion |
| T1485 | Data Destruction (when applicable) |

---

# What I Learned

- File Integrity Monitoring provides visibility into important file changes.
- Wazuh can detect file creation, modification, and deletion events.
- Monitoring critical directories helps identify suspicious or unauthorized changes.
