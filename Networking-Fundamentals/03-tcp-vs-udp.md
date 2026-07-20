# Phase 1 — Networking Fundamentals

![03_tcp_vs_udp](../assets/networking/03_tcp_vs_udp.png)

# Concept 3: TCP vs UDP

## Definition

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are Transport Layer (Layer 4) protocols responsible for transferring data between devices.

The main difference is:

* TCP prioritizes reliability.
* UDP prioritizes speed.

---

# TCP (Transmission Control Protocol)

## Definition

TCP is a connection-oriented protocol. Before data is transmitted, a connection is established between the sender and receiver.

## Characteristics

* Reliable
* Connection-oriented
* Ordered delivery
* Error checking
* Retransmits lost packets
* Slower than UDP

## Common Applications

| Service | Port |
| ------- | ---- |
| HTTP    | 80   |
| HTTPS   | 443  |
| SSH     | 22   |
| FTP     | 21   |
| SMTP    | 25   |
| MySQL   | 3306 |

## Real-Life Analogy

TCP is like a courier service:

* Package is sent.
* Delivery is tracked.
* Receiver confirms receipt.
* Lost packages are resent.

---

# UDP (User Datagram Protocol)

## Definition

UDP is a connectionless protocol. Data is sent immediately without establishing a connection.

## Characteristics

* Fast
* Lightweight
* Connectionless
* No guarantee of delivery
* No packet ordering
* No retransmission

## Common Applications

| Service | Port  |
| ------- | ----- |
| DNS     | 53    |
| DHCP    | 67/68 |
| NTP     | 123   |
| SNMP    | 161   |

## Real-Life Analogy

UDP is like throwing newspapers at houses:

* No confirmation.
* No tracking.
* Speed is more important.

---

# TCP vs UDP

| Feature          | TCP    | UDP    |
| ---------------- | ------ | ------ |
| Reliable         | Yes    | No     |
| Connection       | Yes    | No     |
| Ordered Delivery | Yes    | No     |
| Retransmission   | Yes    | No     |
| Speed            | Slower | Faster |

---

# VAPT Perspective

Common TCP scan:

```bash
nmap -sS target-ip
```

Common UDP scan:

```bash
nmap -sU target-ip
```

Examples:

* Burp Suite mainly works with TCP traffic.
* DNS commonly uses UDP.
* Streaming and gaming often use UDP.

---

# Memory Trick

```text
TCP = Reliable + Slower

UDP = Fast + Lightweight
```

---

# Interview Answer

TCP is a reliable, connection-oriented protocol that guarantees packet delivery and ordering. UDP is a connectionless protocol that prioritizes speed and does not guarantee delivery.
