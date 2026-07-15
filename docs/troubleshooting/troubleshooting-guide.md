# Troubleshooting Guide

This document summarizes the common issues encountered during the SOC lab and the steps taken to resolve them.

---

# Wazuh Agent Disconnected

## Problem

The Wazuh agent appeared as disconnected in the Wazuh Dashboard.

## Possible Cause

- Incorrect Manager IP address
- Network connectivity issues
- Wazuh Agent service stopped

## Solution

- Verified the Manager IP configuration.
- Confirmed network connectivity between the agent and the manager.
- Restarted the Wazuh Agent service.
- Verified that the agent status changed to **Active**.

---

# Auditd Not Generating Events

## Problem

Auditd was installed, but expected events were not appearing in the Wazuh Dashboard.

## Possible Cause

- Auditd service was not running.
- Required audit rules were missing.
- Configuration changes were not applied.

## Solution

- Verified the Auditd service status.
- Reviewed the configured audit rules.
- Restarted the Auditd service after updating the configuration.

---

# SSH Detection Not Working

## Problem

SSH login events were not detected.

## Possible Cause

- SSH service was not running.
- Wazuh Agent was disconnected.
- Auditd configuration was incomplete.

## Solution

- Verified the SSH service status.
- Confirmed the Wazuh Agent connection.
- Checked Auditd configuration and generated a new test event.

---

# File Integrity Monitoring Not Detecting Changes

## Problem

File creation, modification, or deletion events were not generated.

## Possible Cause

- Directory was not configured for monitoring.
- File Integrity Monitoring required additional time to detect changes.

## Solution

- Verified the monitored directory configuration.
- Generated new file events.
- Confirmed that the events appeared in the Wazuh Dashboard.

---

# Wazuh Manager Service Stopped

## Problem

The Wazuh Dashboard stopped receiving new events.

## Possible Cause

- Wazuh Manager service was not running.

## Solution

- Verified the service status.
- Restarted the Wazuh Manager.
- Confirmed that agents reconnected successfully.

---

# Oracle VirtualBox Networking

## Problem

The virtual machines could not communicate with each other.

## Possible Cause

- Incorrect network adapter configuration.

## Solution

- Verified the selected network mode.
- Updated the adapter configuration as required.
- Confirmed connectivity using the `ping` command.

---

# Lessons Learned

Troubleshooting was an important part of this project. Resolving configuration issues helped me understand how different components of the SOC lab communicate and how to identify problems affecting log collection and event detection.
