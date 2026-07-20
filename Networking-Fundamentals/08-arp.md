# Phase 1 — Networking Fundamentals

![08_arp](../assets/networking/08_arp.png)

# Concept 8: ARP (Address Resolution Protocol)

## Definition

ARP is a protocol used to map an IP address (Layer 3 - Logical) to a MAC address (Layer 2 - Physical) on a local area network (LAN).

For devices to communicate on the same local network, knowing the target's IP address is not enough. The sender must know the physical hardware address (MAC address) of the destination device's network card. ARP bridges this gap.

---

## How ARP Works (The Process)

When Device A wants to send data to Device B on the same network, it needs Device B's MAC address.

1. **ARP Cache Check:** Device A checks its internal ARP Cache (a table storing recent IP-to-MAC mappings). If the MAC is found, communication begins.
2. **ARP Request (Broadcast):** If the MAC is not in the cache, Device A sends a broadcast message to every device on the network: *"Who has IP 192.168.1.50? Tell 192.168.1.10."*
3. **ARP Reply (Unicast):** The device that actually has the IP `192.168.1.50` responds directly to Device A: *"I am 192.168.1.50, and my MAC address is 00:1A:2B:3C:4D:5E."*
4. **Cache Update:** Device A saves this mapping in its ARP Cache for future use, and the data transmission occurs.

---

## Real-World Analogy

Imagine being in a crowded office.
* You know you need to hand a document to "John Smith" (IP address), but you don't know what he looks like (MAC address).
* You shout to the entire room (ARP Request broadcast): *"Who is John Smith?"*
* Everyone hears you, but only John Smith answers (ARP Reply unicast): *"I am John Smith, I'm sitting right here."*
* You write down his desk location in your notebook (ARP Cache) so you don't have to shout next time.

---

## VAPT Perspective

ARP has no built-in authentication, which makes it highly vulnerable to attacks on local networks.

* **ARP Spoofing / ARP Poisoning:** An attacker sends forged ARP Replies to a victim device, claiming that the attacker's MAC address is associated with the Default Gateway's IP address.
* The victim's ARP cache is "poisoned," and they start sending all their internet-bound traffic to the attacker instead of the actual router.
* This is the classic setup for a **Man-in-the-Middle (MitM)** attack, allowing the attacker to intercept, read, or modify data in transit.

---

## Key Takeaways

* ARP translates logical IP addresses into physical MAC addresses.
* It operates strictly within a local network (broadcast domain).
* Devices maintain an ARP Cache to speed up subsequent communications.
* Because ARP does not verify identities, it is heavily targeted for Man-in-the-Middle attacks via ARP Poisoning.

---

## Memory Formula

```text
ARP = Maps IP (Layer 3) -> MAC (Layer 2)
```

---

## Interview Answer

**What is ARP and why is it necessary?**

ARP stands for Address Resolution Protocol. It is necessary because data on a local network is delivered using physical MAC addresses, but applications communicate using logical IP addresses. ARP acts as the translator, broadcasting a request to find the MAC address associated with a specific IP address, allowing local network communication to successfully occur.
