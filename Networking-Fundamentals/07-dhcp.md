# Phase 1 — Networking Fundamentals

![07_dhcp](../assets/networking/07_dhcp.png)

# Concept 7: DHCP (Dynamic Host Configuration Protocol)

## Definition

DHCP is a network protocol used to automatically assign IP addresses and other necessary network configuration parameters to devices on a network. 

Instead of a network administrator manually typing an IP address, subnet mask, default gateway, and DNS server into every single computer (static IP), the DHCP server handles this automatically (dynamic IP).

---

## The D.O.R.A. Process

When a new device connects to a network, it obtains an IP address through a four-step process known as **D.O.R.A.**:

### 1. Discover (Client to Server)
The client broadcasts a "DHCP Discover" message to the entire local network (`255.255.255.255`), effectively shouting, "Is there a DHCP server out there?"

### 2. Offer (Server to Client)
Any available DHCP server responds with a "DHCP Offer," suggesting an available IP address, subnet mask, and lease duration.

### 3. Request (Client to Server)
The client broadcasts a "DHCP Request" message accepting the offered IP address. (It broadcasts this so if multiple servers made an offer, the others know their offers were rejected).

### 4. Acknowledge (Server to Client)
The server confirms the assignment with a "DHCP Acknowledge" (ACK) message, and the client configures its network interface.

---

## Lease Time

DHCP does not give away IP addresses permanently; it *leases* them. 
A lease time specifies how long a device can use the assigned IP address before it must renew it. This ensures that IP addresses are not wasted if a device leaves the network.

---

## VAPT Perspective

DHCP plays a critical role in local network security. During a pentest, several DHCP attacks can be executed:

* **DHCP Starvation Attack:** An attacker floods the DHCP server with fake requests using randomized MAC addresses, exhausting the pool of available IP addresses. Legitimate users are then unable to join the network.
* **Rogue DHCP Server:** An attacker introduces their own DHCP server to the network. When victims request an IP, the rogue server assigns them one, but sets the Default Gateway or DNS server to the attacker's machine. This allows for devastating Man-in-the-Middle (MitM) attacks.

---

## Key Takeaways

* DHCP automates the assignment of IP addresses and network configurations.
* The assignment process follows the D.O.R.A. framework (Discover, Offer, Request, Acknowledge).
* IPs are leased for a specific duration, not given permanently.
* Attackers can exploit DHCP through Starvation attacks or by deploying Rogue DHCP servers to intercept traffic.

---

## Memory Formula

```text
D.O.R.A. = Discover -> Offer -> Request -> Acknowledge
```

---

## Interview Answer

**How does DHCP work?**

DHCP automatically configures network devices using a four-step process called D.O.R.A. First, the client broadcasts a **Discover** message. The DHCP server responds with an **Offer** containing an IP address. The client sends a **Request** to accept the offer, and the server finalizes the lease with an **Acknowledge** message, allowing the device to communicate on the network.
