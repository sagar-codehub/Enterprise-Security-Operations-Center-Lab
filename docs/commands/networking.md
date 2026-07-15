# Networking Commands

This document contains networking commands used while setting up and troubleshooting the SOC lab.

---

# Check IP Address

```bash
ip addr
```

Displays network interface information.

---

## Test Connectivity

```bash
ping <IP_Address>
```

Verifies connectivity between machines.

---

## Check Listening Ports

```bash
sudo ss -tulnp
```

Displays listening TCP and UDP ports.

---

## Check SSH Port

```bash
sudo netstat -tulnp | grep ssh
```

Verifies that SSH is listening.

---

## Verify Hostname

```bash
hostname
```

Displays the current hostname.
