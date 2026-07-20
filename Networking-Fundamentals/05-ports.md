# Phase 1 — Networking Fundamentals

![05_network_ports](../assets/networking/05_network_ports.png)

# Concept 5: Network Ports and Sockets

## Definition and Core Concepts

In computer networking, an IP address acts as the unique identifier for a physical machine or host on a network. However, modern computers are capable of running dozens, if not hundreds, of network applications simultaneously. A server might be running a web server, an email server, an SSH daemon, and a database all at the exact same time, on the exact same IP address.

How does the network stack know which application should receive incoming data? This is where **Network Ports** come into play.

A network port is a 16-bit logical, virtual endpoint for communication within an operating system. While the IP address identifies the *computer*, the port number identifies the specific *application or service* running on that computer.

### The Concept of a Socket
When an IP address is combined with a port number, it creates a **Socket**. 
For example, if a server's IP is `192.168.1.50`, and it is running a web server on port `80`, the resulting socket is written as `192.168.1.50:80`.

Data sent across the internet is always addressed from a source socket to a destination socket.

---

## Real-World Analogy: The Corporate Office

To visualize this, imagine a large corporate office building.
* The **IP Address** is the street address of the building (e.g., 123 Tech Boulevard). This gets the postman to the correct building.
* The **Port Number** is the specific department or desk extension inside the building (e.g., Extension 80 for Marketing, Extension 22 for IT Support).
* The **Socket** is the full mailing address: "123 Tech Boulevard, Desk 80."

If you deliver a package to the building without a desk number, the receptionist (the OS network stack) won't know who to give it to, and it will be dropped.

---

## Port Number Categorization

Because port numbers are 16-bit binary integers, the total number of available ports on any given system ranges from **0 to 65535**. 
The Internet Assigned Numbers Authority (IANA) divides these into three distinct ranges to maintain order and standardization across the internet.

### 1. Well-Known Ports / System Ports (0 - 1023)
These ports are strictly reserved for standard, universally recognized system services and legacy protocols. On Unix/Linux systems, binding an application to one of these ports requires root/administrator privileges. This prevents unprivileged users from spinning up fake web servers or SSH daemons.

**Crucial Well-Known Ports for VAPT:**
* **20/21** - FTP (File Transfer Protocol): Unencrypted file transfer. (Highly vulnerable to sniffing).
* **22** - SSH (Secure Shell): Encrypted remote administration. (Target for brute forcing).
* **23** - Telnet: Unencrypted remote administration. (Legacy, highly insecure).
* **25** - SMTP (Simple Mail Transfer Protocol): Email routing.
* **53** - DNS (Domain Name System): Domain resolution. (Often UDP, but uses TCP for zone transfers).
* **80** - HTTP (Hypertext Transfer Protocol): Unencrypted web traffic.
* **110/143** - POP3 / IMAP: Email retrieval.
* **139/445** - SMB (Server Message Block): Windows file sharing. (Infamous for EternalBlue/WannaCry exploits).
* **443** - HTTPS (HTTP Secure): Encrypted web traffic.

### 2. Registered Ports (1024 - 49151)
These ports are typically used by specific software applications, vendor-specific protocols, and databases. While not as universally strict as well-known ports, vendors register these with IANA to avoid conflicts.

**Common Registered Ports:**
* **1433** - Microsoft SQL Server (Database)
* **1521** - Oracle Database
* **3306** - MySQL / MariaDB (Database)
* **3389** - RDP (Remote Desktop Protocol): Windows graphical remote control.
* **5432** - PostgreSQL (Database)
* **8080 / 8443** - HTTP Alternate (Commonly used by Tomcat, proxies, and development web servers).

### 3. Dynamic / Private / Ephemeral Ports (49152 - 65535)
These ports are rarely bound to listening services. Instead, they are used as **Ephemeral (temporary) source ports** for outbound connections.

When you open your web browser and navigate to `https://google.com` (Destination Port 443), your OS must open a local port to receive the response. The OS randomly selects a high port (e.g., 51234) for this specific browser tab. 
The resulting connection looks like: `Your_IP:51234  <--->  Google_IP:443`.
Once you close the tab, port 51234 is released back to the OS.

---

## VAPT Perspective: Port Scanning and Reconnaissance

In penetration testing, identifying open ports is the foundational step of the reconnaissance phase. You cannot attack a service if you do not know it exists.

### The Role of Nmap
**Nmap (Network Mapper)** is the industry-standard tool for port scanning. It works by sending specially crafted packets to a range of ports on a target IP and analyzing the responses.

Nmap classifies ports into several distinct states:
1. **Open:** An application is actively listening for connections on this port. (This is the primary target for attackers).
2. **Closed:** The host is up, but no application is listening on this port. The OS responds with a TCP RST (Reset) packet.
3. **Filtered:** Nmap cannot determine if the port is open or closed because packet filtering (a firewall) is silently dropping the probes.
4. **Unfiltered:** The port is accessible, but Nmap cannot determine if it is open or closed (usually seen during ACK scans).

### Port Scanning Strategies

* **Full 65k Scan:** Scanning all 65,535 ports ensures you don't miss obscure services hidden on high ports (e.g., an admin panel running on port 44444).
  ```bash
  nmap -p- 192.168.1.50
  ```
* **Top Ports Scan:** To save time, Nmap scans the top 1,000 most common ports by default. You can restrict this further to evade detection.
  ```bash
  nmap --top-ports 100 192.168.1.50
  ```
* **Service Enumeration (`-sV`):** Simply knowing port 80 is open is not enough. A pentester must know exactly what application and version is running behind that port to search for CVEs (exploits).
  ```bash
  nmap -sV -p 80,443 192.168.1.50
  ```

### Common Exploitation Vectors based on Ports
* **Port 21 (FTP) / 23 (Telnet):** Because these are unencrypted, an attacker can use a tool like Wireshark or tcpdump on the local network to sniff plaintext usernames and passwords.
* **Port 22 (SSH) / 3389 (RDP):** These are prime targets for automated brute-force attacks or password spraying using tools like Hydra or CrackMapExec.
* **Port 139/445 (SMB):** Historically the most vulnerable ports in Windows environments, exploited for remote code execution (RCE) and lateral movement (e.g., Pass-the-Hash).
* **Database Ports (3306, 1433, 5432):** Should never be exposed directly to the internet. If discovered on a public IP, they are targeted for default credential attacks or SQL injection if misconfigured.

---

## Deep Dive: TCP vs UDP Ports

It is vital to understand that the port space for TCP and UDP are completely separate. 
TCP Port 53 and UDP Port 53 are two entirely different endpoints.

* A machine can run a DNS server listening on **UDP Port 53**.
* Simultaneously, it can run a completely different application listening on **TCP Port 53**.
(Though practically, DNS uses both, the operating system treats them as isolated channels).

When writing firewall rules or conducting port scans, you must specify the protocol:
```bash
# Allow TCP 80
iptables -A INPUT -p tcp --dport 80 -j ACCEPT

# Allow UDP 53
iptables -A INPUT -p udp --dport 53 -j ACCEPT
```

---

## Host-Based Troubleshooting

As a security engineer or system administrator, you must be able to identify what ports your own system is exposing. A compromised machine will often open a high port (e.g., a reverse shell or backdoor listening on port 4444).

### Using `ss` and `netstat` (Linux)
```bash
# Show listening TCP and UDP ports, and the associated process ID/Name
ss -tulpn
netstat -tulpn
```
* `-t`: TCP ports
* `-u`: UDP ports
* `-l`: Listening sockets only
* `-p`: Show the Process ID (requires root)
* `-n`: Numeric output (do not resolve IPs to hostnames or ports to service names)

### Using `lsof` (Linux)
```bash
# Find out exactly what process is bound to port 8080
lsof -i :8080
```

### Using `netstat` (Windows)
```cmd
netstat -ano | findstr LISTENING
```

---

## Port Forwarding and NAT

In home networks or Docker environments, a router or host machine possesses the public IP address, while internal devices/containers use private IPs.

**Port Forwarding** maps a port on the public IP to a specific socket on the internal network.
* External Request: `Public_IP:8080`
* Router Translates to: `Private_IP:80`

This concept is essential for pivoting during a penetration test, where an attacker compromises an edge server and uses SSH local port forwarding to access internal database ports.

---

## Key Takeaways

* Ports allow a single IP address to host multiple distinct services simultaneously.
* The combination of an IP address and a Port is called a Socket.
* Port numbers range from 0 to 65535, divided into Well-Known, Registered, and Ephemeral ranges.
* Port 0 to 1023 require root/admin privileges to bind on Unix systems.
* Nmap is the standard tool for discovering open ports, which is the first step in identifying the attack surface of a target.
* TCP and UDP maintain entirely separate port spaces.
* Tools like `ss`, `netstat`, and `lsof` are critical for monitoring local open ports and detecting unauthorized backdoors.

---

## Memory Formula

```text
IP Address = Street Address of the Building
Port Number = Department / Room Number
Socket = IP + Port (192.168.1.10:443)
```

---

## Interview Questions & Answers

**Q: What is the difference between a Well-Known port and an Ephemeral port?**
**A:** Well-known ports (0-1023) are reserved for standard, established services like HTTP (80) and SSH (22). They typically require root privileges to bind to. Ephemeral ports (49152-65535) are temporary, high-numbered ports dynamically assigned by the operating system to client applications (like a web browser) when they initiate an outbound connection. Once the connection closes, the ephemeral port is released.

**Q: Can you run two different applications on Port 80 on the same IP address?**
**A:** No, not on the same protocol. You cannot have two applications binding to TCP port 80 on the same IP address simultaneously; the OS will throw a "port already in use" or "bind exception" error. However, you *can* have one application on TCP port 80 and a completely different application on UDP port 80, as they are separate protocols. Additionally, using virtual hosts/reverse proxies (like Nginx), one application on port 80 can route traffic to multiple backend applications on different internal ports.

**Q: An Nmap scan shows a port as "Filtered". What does this mean?**
**A:** A "Filtered" state indicates that Nmap cannot determine whether the port is open or closed because network traffic is being blocked, typically by a firewall or router ACL. The probes sent by Nmap are either being dropped silently without a response, or the firewall is responding with an ICMP error message explicitly rejecting the traffic.
