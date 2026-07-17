# Phase 1 — Networking Fundamentals

# Concept 4: TCP Three-Way Handshake

## Definition

The TCP Three-Way Handshake is the process used by TCP to establish a connection between a client and a server before exchanging data.

It ensures that both sides are ready to communicate.

---

# Why Do We Need It?

Before sending sensitive information such as:

* Passwords
* Bank transactions
* Emails
* API requests

both systems must confirm that they can communicate.

---

# The Three Steps

## Step 1: SYN

The client sends:

```text
SYN
```

Meaning:

> "Can we communicate?"

---

## Step 2: SYN-ACK

The server replies:

```text
SYN-ACK
```

Meaning:

> "Yes, I received your request."

---

## Step 3: ACK

The client sends:

```text
ACK
```

Meaning:

> "Great, let's start."

---

# Full Flow

```text
Client                 Server

SYN      ---------->

          <----------   SYN-ACK

ACK      ---------->
```

Connection established.

---

# Real-Life Analogy

Imagine making a phone call:

```text
You: "Hello?"

Friend: "Hello, I can hear you."

You: "Perfect."
```

Only after this conversation starts can you exchange information.

---

# Where Is It Used?

Every TCP service uses the handshake:

* HTTP
* HTTPS
* SSH
* FTP
* Databases

---

# VAPT Perspective

Nmap SYN scans depend on the three-way handshake.

Example:

```bash
nmap -sS target-ip
```

Nmap sends a SYN packet and analyzes the response:

| Response    | Meaning        |
| ----------- | -------------- |
| SYN-ACK     | Port is open   |
| RST         | Port is closed |
| No response | Filtered       |

---

# SYN Flood Attack

An attacker sends thousands of SYN packets but never completes the handshake.

```text
Attacker → SYN
Server → SYN-ACK
```

The server waits for the final ACK and eventually runs out of resources.

This is called a SYN Flood attack.

---

# Memory Trick

```text
SYN

↓

SYN-ACK

↓

ACK
```

Think:

```text
"Can we talk?"

"Yes."

"Okay."
```

---

# Key Takeaways

* TCP uses a three-way handshake before communication.
* The sequence is SYN → SYN-ACK → ACK.
* It ensures both devices are ready.
* Nmap and firewalls rely heavily on this process.
* SYN flood attacks exploit the handshake.

---

# Interview Answer

The TCP Three-Way Handshake is the connection establishment process used by TCP. It consists of SYN, SYN-ACK, and ACK packets exchanged between the client and server before data transmission begins.
