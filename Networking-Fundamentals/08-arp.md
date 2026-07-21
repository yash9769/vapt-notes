# Phase 1 — Networking Fundamentals

# Concept 8: ARP (Address Resolution Protocol)

## Definition

ARP converts an IP address into a MAC address inside a local network.

Example:

```text
192.168.1.5

↓

00:1A:2B:3C:4D:5E
```

---

# Why Do We Need ARP?

Devices communicate on the local network using MAC addresses.

Suppose your laptop knows:

```text
192.168.1.10
```

but needs the corresponding MAC address. ARP helps find it.

---

# How ARP Works

## Step 1

The sender broadcasts:

```text
"Who has 192.168.1.10?"
```

---

## Step 2

The target device replies:

```text
"I have 192.168.1.10."

"My MAC address is 00:1A:2B:3C:4D:5E."
```

---

## Step 3

The sender stores this information in the ARP cache.

---

# ARP Flow

```text
Laptop                  Network

Who has 192.168.1.10? ----->

          <----- MAC address response
```

---

# View the ARP Table

Windows:

```powershell
arp -a
```

Linux:

```bash
arp -a
```

or

```bash
ip neigh
```

---

# VAPT Perspective

ARP is vulnerable to ARP spoofing.

Attackers can impersonate another device and intercept traffic.

Example:

* Man-in-the-Middle (MITM)
* Packet sniffing
* Session hijacking

Tools:

* Bettercap
* Ettercap

---

# Memory Trick

```text
ARP

IP Address → MAC Address
```

---

# Interview Answer

ARP resolves IP addresses into MAC addresses within a local network. It allows devices to communicate at the Data Link layer.
