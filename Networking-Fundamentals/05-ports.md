# Phase 1 — Networking Fundamentals

# Concept 5: Ports

## Definition

A port is a logical communication endpoint on a device. Ports allow multiple services to run simultaneously on the same IP address.

Think of:

```text
IP Address = Building

Port = Room Number
```

Even though a building has one address, different rooms serve different purposes.

---

# Why Do We Need Ports?

A single server may run:

* A website
* A database
* SSH access
* Email services

Ports help the operating system decide which application should receive the incoming data.

---

# Port Ranges

## Well-Known Ports (0–1023)

Reserved for common services.

Examples:

| Service | Port |
| ------- | ---- |
| FTP     | 21   |
| SSH     | 22   |
| Telnet  | 23   |
| SMTP    | 25   |
| DNS     | 53   |
| HTTP    | 80   |
| HTTPS   | 443  |

---

## Registered Ports (1024–49151)

Used by applications and software.

Examples:

| Service    | Port  |
| ---------- | ----- |
| MySQL      | 3306  |
| PostgreSQL | 5432  |
| MongoDB    | 27017 |

---

## Dynamic/Ephemeral Ports (49152–65535)

Temporary ports assigned by the operating system to clients.

Example:

When your browser connects to GitHub:

```text
Your Laptop:
192.168.1.10:54231

↓

GitHub:
140.82.x.x:443
```

Port 54231 is temporary and chosen automatically.

---

# Common Ports for VAPT

| Port | Service    |
| ---- | ---------- |
| 21   | FTP        |
| 22   | SSH        |
| 23   | Telnet     |
| 25   | SMTP       |
| 53   | DNS        |
| 80   | HTTP       |
| 110  | POP3       |
| 139  | NetBIOS    |
| 143  | IMAP       |
| 443  | HTTPS      |
| 445  | SMB        |
| 3306 | MySQL      |
| 3389 | RDP        |
| 5432 | PostgreSQL |

---

# Port States in Nmap

## Open

A service is actively listening.

Example:

```text
22/tcp open ssh
```

---

## Closed

No service is listening.

---

## Filtered

A firewall is blocking the traffic.

---

# Useful Nmap Commands

Scan the top ports:

```bash
nmap target-ip
```

Scan all ports:

```bash
nmap -p- target-ip
```

Scan specific ports:

```bash
nmap -p 22,80,443 target-ip
```

---

# VAPT Perspective

Open ports indicate the attack surface of a system.

Examples:

* Port 22 → SSH brute-force testing.
* Port 80 → Web application testing.
* Port 3306 → Database exposure.
* Port 445 → SMB vulnerabilities.

Attackers and penetration testers always begin by identifying open ports.

---

# Memory Trick

```text
IP Address = Building

Port = Room Number
```

Without the room number, the message cannot reach the correct service.

---

# Interview Answer

Ports are logical communication endpoints used by the operating system to direct network traffic to the correct service. Different applications use different ports, such as HTTP on port 80 and HTTPS on port 443.
