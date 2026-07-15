# Linux Commands

This document contains the Linux commands used during the SOC lab.

---

# SSH

## Check SSH Service

```bash
sudo systemctl status ssh
```

Checks whether the SSH service is running.

---

## Start SSH

```bash
sudo systemctl start ssh
```

Starts the SSH service.

---

## Restart SSH

```bash
sudo systemctl restart ssh
```

Restarts the SSH service.

---

## Connect via SSH

```bash
ssh username@<Ubuntu_Desktop_IP>
```

Connects to the Ubuntu Desktop from Kali Linux.

---

# User Management

## Create User

```bash
sudo useradd socuser
```

Creates a new Linux user.

---

## Verify User

```bash
id socuser
```

Displays information about the specified user.

---

## Delete User

```bash
sudo userdel socuser
```

Deletes the specified user.

---

# Privilege Escalation

```bash
sudo apt update
```

Executes a command with elevated privileges.

---

# Auditd

## Install Auditd

```bash
sudo apt install auditd audispd-plugins
```

Installs Auditd.

---

## Check Auditd Status

```bash
sudo systemctl status auditd
```

Checks whether Auditd is running.

---

## Restart Auditd

```bash
sudo systemctl restart auditd
```

Restarts the Auditd service.

---

# SSH Configuration

```bash
sudo nano /etc/ssh/sshd_config
```

Opens the SSH configuration file.

---

# Cron

## Edit Cron Jobs

```bash
crontab -e
```

Creates or edits scheduled tasks.

---

## View Cron Jobs

```bash
crontab -l
```

Displays configured cron jobs.

---

# Sensitive Files

## Read /etc/passwd

```bash
sudo cat /etc/passwd
```

Displays local user information.

---

## Read /etc/shadow

```bash
sudo cat /etc/shadow
```

Displays password information.

---

# Log Monitoring

```bash
sudo nano /var/log/auth.log
```

Used to generate a log modification event.

---

# Systemd

## Create a Service

```bash
sudo nano /etc/systemd/system/test.service
```

Creates a new systemd service.

---

## Reload Systemd

```bash
sudo systemctl daemon-reload
```

Reloads the systemd manager.

---

## Enable Service

```bash
sudo systemctl enable test.service
```

Starts the service automatically during boot.
