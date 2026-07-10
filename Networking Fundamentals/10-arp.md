# ARP

## Definition
ARP stands for Address Resolution Protocol. It maps an IP address to a MAC address on the same local network.

## Why it exists
- Devices need MAC addresses to send data on the local network.
- IP addresses are logical, but Ethernet communication uses MAC addresses.
- ARP helps bridge the gap between Layer 3 and Layer 2.

## Simple explanation
ARP asks: “Which device has this IP address? What is its MAC address?”

## How it works
1. A device wants to send data to another device on the same network.
2. It checks its ARP table.
3. If the MAC address is not known, it sends an ARP request.
4. The target device replies with its MAC address.

## Interview points
- What is ARP?
- Why is ARP used?
- What is the difference between ARP and DNS?

## Quick revision
- ARP = IP to MAC
- Used inside the local network
- Helps devices communicate at Layer 2
