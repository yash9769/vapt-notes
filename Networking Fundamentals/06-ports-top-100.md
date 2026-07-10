# Ports Top 100

## Definition
Ports are numeric endpoints used by network services to identify specific applications or processes on a device.

## Why they exist
- They allow multiple services to run on the same device.
- They help the operating system send data to the correct application.
- Without ports, a device would not know which program should receive incoming traffic.

## Simple explanation
An IP address identifies the device, and a port identifies the service on that device.

Example:
- IP address = house address
- Port = room number inside the house

## Common port categories
- Well-known ports: 0–1023
- Registered ports: 1024–49151
- Dynamic/private ports: 49152–65535

## Important ports

| Port | Protocol | Service | Use |
|---|---|---|---|
| 21 | TCP | FTP | File transfer |
| 22 | TCP | SSH | Secure remote access |
| 23 | TCP | Telnet | Older insecure remote login |
| 25 | TCP | SMTP | Sending email |
| 53 | UDP/TCP | DNS | Domain name resolution |
| 67/68 | UDP | DHCP | IP address assignment |
| 80 | TCP | HTTP | Web traffic |
| 110 | TCP | POP3 | Receiving email |
| 119 | TCP | NNTP | Usenet |
| 123 | UDP | NTP | Time synchronization |
| 135 | TCP/UDP | RPC | Windows service communication |
| 139 | TCP/UDP | NetBIOS | Windows file and printer sharing |
| 143 | TCP | IMAP | Email retrieval |
| 161/162 | UDP | SNMP | Network monitoring |
| 389 | TCP/UDP | LDAP | Directory services |
| 443 | TCP | HTTPS | Secure web traffic |
| 445 | TCP | SMB | Windows file sharing |
| 465 | TCP | SMTPS | Secure SMTP |
| 587 | TCP | Submission | Secure mail submission |
| 993 | TCP | IMAPS | Secure IMAP |
| 995 | TCP | POP3S | Secure POP3 |
| 1433 | TCP | MSSQL | Microsoft SQL Server |
| 1521 | TCP | Oracle | Oracle database |
| 3306 | TCP | MySQL | MySQL database |
| 3389 | TCP | RDP | Remote Desktop |
| 5900 | TCP | VNC | Remote desktop access |
| 8080 | TCP | HTTP alternate | Web proxy or app server |
| 8443 | TCP | HTTPS alternate | Secure web alternate |

## Top interview points
- Port numbers help direct traffic to the correct service.
- HTTP uses 80, HTTPS uses 443.
- SSH uses 22.
- DNS uses 53.
- RDP uses 3389.

## Real-world example
When you open a website:
- your browser connects to port 443 for HTTPS.
- your email client may use port 587 or 993.
- your remote desktop tool may use port 3389.

## Common mistakes
- Confusing IP address with port number.
- Assuming all services use the same port.
- Forgetting that TCP and UDP can use the same port number for different services.

## Memory tricks
- 80 = HTTP
- 443 = HTTPS
- 22 = SSH
- 53 = DNS
- 3389 = RDP

## Quick revision
- IP = device
- Port = service
- 80 = HTTP
- 443 = HTTPS
- 22 = SSH
- 53 = DNS
- 3389 = RDP

## Exam summary
Ports are important because they let one host run many services at the same time. Knowing the most common ports is essential for networking, system administration, and security interviews.
