# Phase 1 — Networking Fundamentals

# Concept 9: ICMP (Internet Control Message Protocol)

## Definition

ICMP is used to send network status and error messages between devices.

It does not transfer application data like HTTP or FTP.

---

# Why Do We Need ICMP?

ICMP helps devices determine:

* Whether a host is reachable.
* Whether packets were lost.
* Whether a route exists.
* Network latency.

---

# Common ICMP Messages

| Message                 | Purpose            |
| ----------------------- | ------------------ |
| Echo Request            | Sent by ping       |
| Echo Reply              | Response to ping   |
| Destination Unreachable | Host not reachable |
| Time Exceeded           | TTL expired        |

---

# Ping

When you run:

```bash
ping google.com
```

your computer sends:

```text
ICMP Echo Request
```

Google responds with:

```text
ICMP Echo Reply
```

---

# Traceroute

Traceroute uses ICMP to discover all routers between you and the destination.

Windows:

```powershell
tracert google.com
```

Linux:

```bash
traceroute google.com
```

---

# TTL (Time To Live)

Every packet has a TTL value.

Each router decreases the TTL by 1.

When TTL becomes zero:

```text
ICMP Time Exceeded
```

is sent back.

---

# VAPT Perspective

Security testers use ICMP to:

* Check whether systems are alive.
* Map networks.
* Measure latency.

Example:

```bash
nmap -sn 192.168.1.0/24
```

---

# Security Note

Many organizations block ICMP to reduce reconnaissance.

However, blocking ICMP completely can create network troubleshooting issues.

---

# Memory Trick

```text
ICMP = Network Messenger
```

It carries error and status messages.

---

# Interview Answer

ICMP is a protocol used for network diagnostics and error reporting. Commands such as ping and traceroute rely on ICMP.
