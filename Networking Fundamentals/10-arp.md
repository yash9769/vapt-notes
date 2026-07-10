# ARP

## Definition
ARP stands for Address Resolution Protocol. It maps an IP address to a MAC address on the same local network.

## Why it exists
- IP addresses are used for logical routing.
- Ethernet and Wi-Fi communication need MAC addresses.
- ARP helps connect these two layers so devices can talk to each other locally.

## Simple explanation
ARP asks a question:
- “Which MAC address belongs to this IP address?”

## Real-life analogy
Think of ARP like a receptionist finding the correct room number for a person.
- You know the person’s name.
- You need the exact room to reach them.

ARP does the same thing for IP and MAC addresses.

## How it works
1. A device wants to send data to another device on the same subnet.
2. It checks its ARP table for a cached MAC address.
3. If not found, it broadcasts an ARP request.
4. The target device replies with its MAC address.
5. The sender stores the result and sends the data.

## ARP table
The ARP table stores known IP-to-MAC mappings so the device does not need to ask every time.

## Common interview points
- What is ARP?
- Why is ARP needed?
- What is the difference between ARP and DNS?
- What is an ARP request and ARP reply?

## Real-world example
When your laptop wants to send data to another laptop in the same office Wi-Fi network:
- it uses ARP to discover the MAC address
- then it can send the frame directly on the local network

## Common mistakes
- Confusing ARP with DNS.
- Forgetting that ARP works only on the local network.
- Thinking ARP is used across the internet.

## Memory trick
ARP = Address Resolution Protocol
Think: ARP = IP to MAC

## Quick revision
- ARP maps IP to MAC
- It is used inside the local network
- It helps Layer 2 communication
