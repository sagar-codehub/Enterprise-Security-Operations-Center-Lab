# Troubleshooting Commands

This document contains commands frequently used while troubleshooting the SOC lab.

---

# Check Services

```bash
sudo systemctl status ssh
sudo systemctl status auditd
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-agent
```

---

# Restart Services

```bash
sudo systemctl restart ssh
sudo systemctl restart auditd
sudo systemctl restart wazuh-manager
sudo systemctl restart wazuh-agent
```

---

# Verify User

```bash
id username
```

---

# Check Logs

```bash
sudo tail -f /var/ossec/logs/ossec.log
```

Displays Wazuh Manager logs.

---

## Check Authentication Logs

```bash
sudo tail -f /var/log/auth.log
```

Displays authentication logs.

---

## Verify Audit Rules

```bash
sudo auditctl -l
```

Lists active Auditd rules.

---

## Restart Network

```bash
sudo systemctl restart NetworkManager
```

Restarts the network service (if applicable).
