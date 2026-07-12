# Phase 1 — Networking Fundamentals

!(what is a network)(..assets/networking/what-is-a-network.png)

# Concept 1: What is a Network?

## Definition

A network is a collection of two or more devices connected together to exchange data and share resources. These devices communicate using standard networking protocols.

A network allows devices to:

* Exchange information
* Access the internet
* Share files
* Use common resources
* Communicate with each other

---

## Devices in a Network

Common devices found in a network include:

* Computers
* Smartphones
* Servers
* Routers
* Switches
* Printers
* CCTV cameras
* IoT devices

Any device connected to a network is called a **host**.

---

## Core Components of a Network

A network consists of three essential parts:

### 1. Devices

The endpoints that send and receive data.

Examples:

* Laptop
* Mobile phone
* Server

### 2. Communication Medium

The path through which data travels.

Examples:

* Ethernet cable
* Fiber-optic cable
* Wi-Fi

### 3. Protocols

The rules that devices follow to communicate.

Examples:

* TCP
* UDP
* HTTP
* HTTPS
* DNS

---

## Real-World Analogy

Think of a city.

* Houses represent devices.
* Roads represent the network.
* Cars represent data.
* Traffic rules represent protocols.
* Traffic police represent firewalls.

Without roads, houses cannot exchange goods. Similarly, without a network, devices cannot exchange data.

---

## Office Example

Consider a company office containing:

* Employee laptops
* HR systems
* Printers
* Wi-Fi routers
* File servers

All these devices are connected through a network.

Because of the network, employees can:

* Access shared files
* Print documents
* Use internal applications
* Access the internet

Without the network, each device would operate independently.

---

## VAPT Perspective

In a Vulnerability Assessment and Penetration Test (VAPT), the network is the attack surface.

A client may provide an IP range such as:

```text
192.168.10.0/24
```

The first task of a penetration tester is to understand the network by answering questions such as:

* Which devices exist?
* Which ports are open?
* Which services are running?
* Which operating systems are present?
* Which machines are vulnerable?

Tools such as Nmap, Wireshark, and Burp Suite rely on an understanding of the target network.

---

## Why Attackers Target Networks

Attackers rarely target isolated devices. They target networks because compromising one system can provide access to many others.

Example:

```text
Internet
    │
Firewall
    │
Router
    │
───────────────
│      │      │
PC1   PC2   Server
             │
         Database
```

If the server is compromised, an attacker may reach the database and other internal systems.

---

## Types of Networks

### LAN (Local Area Network)

A network that covers a small geographical area.

Examples:

* Home Wi-Fi
* College laboratory
* Office building

---

### WAN (Wide Area Network)

A network that connects multiple LANs across large distances.

Examples:

* Branch offices in different cities
* The Internet

The Internet is the world's largest WAN.

---

## Important Terms

### Host

Any device connected to a network.

### Communication

The exchange of data between devices.

### Resource Sharing

The ability to share files, printers, internet access, and applications.

### Protocol

A set of rules that devices follow while communicating.

---

## Key Takeaways

* A network is a group of interconnected devices.
* Devices communicate using protocols.
* Networks exist to share data and resources.
* Every VAPT engagement starts with understanding the target network.
* Compromising one device can lead to other systems within the network.

---

## Memory Formula

```text
Devices + Communication + Protocols = Network
```

---

## Interview Answer

**What is a computer network?**

A computer network is a collection of interconnected devices that communicate with each other to exchange data and share resources such as files, printers, applications, and internet connectivity using standardized communication protocols.
