# Windows Commands

This document contains the Windows commands used during the SOC lab.

---

# User Management

## Create a Local User

```cmd
net user testuser Password@123 /add
```

Creates a new local user account.

---

## View Local Users

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

## Verify Sysmon Service

Open **Services** and verify that the **Sysmon** service is running.

You can also verify Sysmon events from:

```
Event Viewer
└── Applications and Services Logs
    └── Microsoft
        └── Windows
            └── Sysmon
                └── Operational
```

---

# Registry Monitoring

Open the Registry Editor.

```cmd
regedit
```

Used to view or modify Windows Registry keys.

---

# File Integrity Monitoring

Create, modify, or delete files inside a monitored directory to generate File Integrity Monitoring events.

---

# Useful Commands

## Display Current User

```cmd
whoami
```

Displays the currently logged-in user.

---

## Display Hostname

```cmd
hostname
```

Displays the computer name.
