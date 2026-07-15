# Commands Reference

This document contains the important commands used throughout the SOC lab. The commands are grouped by operating system and functionality for quick reference.

---

# Windows Commands

## Create a Local User

```cmd
net user testuser Password@123 /add
```

Creates a new local user account.

---

## List Local Users

```cmd
net user
```

Displays all local user accounts.

---

# Sysmon

## Install Sysmon

```powershell
Sysmon64.exe -accepteula -i sysmonconfig.xml
```

Installs Sysmon using the specified configuration file.

---

# Linux Commands

## Verify SSH Service

```bash
sudo systemctl status ssh
```

Checks whether the SSH service is running.

---

## Start SSH Service

```bash
sudo systemctl start ssh
```

Starts the SSH service.

---

## Connect Using SSH

```bash
ssh username@<Ubuntu_Desktop_IP>
```

Establishes an SSH connection to the Ubuntu Desktop.

---

## Create a Linux User

```bash
sudo useradd socuser
```

Creates a new local Linux user.

---

## Verify the User

```bash
id socuser
```

Displays information about the specified user.

---

## Delete a Linux User

```bash
sudo userdel socuser
```

Deletes the specified user.

---

## Privilege Escalation

```bash
sudo apt update
```

Executes a command with elevated privileges.

---

# Auditd Commands

## Install Auditd

```bash
sudo apt install auditd audispd-plugins
```

Installs the Linux Audit Daemon.

---

## Check Auditd Status

```bash
sudo systemctl status auditd
```

Verifies whether Auditd is running.

---

## Start Auditd

```bash
sudo systemctl start auditd
```

Starts the Auditd service.

---

## Restart Auditd

```bash
sudo systemctl restart auditd
```

Restarts the Auditd service after configuration changes.

---

# SSH Configuration

## Edit SSH Configuration

```bash
sudo nano /etc/ssh/sshd_config
```

Opens the SSH configuration file.

---

## Restart SSH

```bash
sudo systemctl restart ssh
```

Applies SSH configuration changes.

---

# Cron

## Edit Cron Jobs

```bash
crontab -e
```

Creates or modifies scheduled cron jobs.

---

## View Cron Jobs

```bash
crontab -l
```

Displays configured cron jobs.

---

# Sensitive File Access

## Read /etc/passwd

```bash
sudo cat /etc/passwd
```

Displays user account information.

---

## Read /etc/shadow

```bash
sudo cat /etc/shadow
```

Displays password-related information (requires elevated privileges).

---

# Log Monitoring

## Edit Authentication Log

```bash
sudo nano /var/log/auth.log
```

Used to generate a log modification event during testing.

---

# Systemd

## Create a Service

```bash
sudo nano /etc/systemd/system/test.service
```

Creates a new systemd service file.

---

## Reload Systemd

```bash
sudo systemctl daemon-reload
```

Reloads the systemd manager configuration.

---

## Enable a Service

```bash
sudo systemctl enable test.service
```

Configures the service to start automatically during boot.

---

# Wazuh

During the project, the Wazuh Dashboard was used to:

- Monitor connected agents.
- Review generated alerts.
- Search security events.
- Verify MITRE ATT&CK mappings.
- Investigate Windows and Linux activities.
