# Phase 1 — Networking Fundamentals

# Concept 7: DHCP (Dynamic Host Configuration Protocol)

## Definition

DHCP automatically assigns network configuration to devices connected to a network.

Without DHCP, you would have to manually configure:

* IP address
* Subnet mask
* Default gateway
* DNS server

---

# Why Do We Need DHCP?

Suppose 200 employees join a company's Wi-Fi. Assigning IP addresses manually would be inefficient.

DHCP automates the process.

---

# DHCP Process (DORA)

## Step 1: Discover

The client broadcasts:

```text
"Is there any DHCP server?"
```

---

## Step 2: Offer

The DHCP server replies:

```text
"Use IP address 192.168.1.20."
```

---

## Step 3: Request

The client responds:

```text
"I want to use that IP."
```

---

## Step 4: Acknowledge

The server confirms:

```text
"The IP address is now assigned."
```

---

# DORA Flow

```text
Client                DHCP Server

Discover ---------->

          <---------- Offer

Request ----------->

          <---------- Acknowledge
```

---

# Common Ports

| Protocol    | Port |
| ----------- | ---- |
| DHCP Server | 67   |
| DHCP Client | 68   |

DHCP uses UDP.

---

# VAPT Perspective

Misconfigured DHCP servers can:

* Assign incorrect network settings.
* Enable rogue DHCP attacks.
* Redirect users to malicious DNS servers.

---

# Memory Trick

```text
DORA

D → Discover
O → Offer
R → Request
A → Acknowledge
```

---

# Interview Answer

DHCP automatically assigns IP addresses and other network settings to devices. It uses the DORA process and operates on UDP ports 67 and 68.
