# HTTP and HTTPS

## Definition
HTTP and HTTPS are application layer protocols used to transfer web data between a client and a server.

## Why they exist
- HTTP allows browsers to request and receive web pages.
- HTTPS adds encryption so the data is protected while traveling over the network.
- Without these protocols, websites would not be able to load in a standard way.

## Simple explanation
- HTTP = web traffic without encryption
- HTTPS = web traffic with encryption

## Real-life analogy
Think of HTTP as sending a postcard and HTTPS as sending a sealed letter.
- A postcard can be read by anyone.
- A sealed letter protects the contents.

## Difference
| Protocol | Port | Security | Common use |
|---|---|---|---|
| HTTP | 80 | No encryption | Basic websites |
| HTTPS | 443 | Encrypted | Secure websites, login pages, banking |

## How it works
1. The browser sends a request to the web server.
2. The server responds with the page content.
3. HTTPS adds encryption so attackers cannot easily read the data.

## Common interview points
- What is the difference between HTTP and HTTPS?
- Which port is used by HTTPS?
- Why is HTTPS preferred for login pages?
- What is TLS?

## Real-world example
When you log in to Gmail or Facebook:
- the connection is usually HTTPS
- your password and data are encrypted
- this keeps them safe from network attackers

## Common mistakes
- Thinking HTTPS is a different website type rather than a secure version of HTTP.
- Forgetting that HTTPS uses port 443.
- Believing HTTPS hides all network problems; it only secures the traffic.

## Memory trick
HTTP = HyperText Transfer Protocol
HTTPS = HTTP + Secure

## Quick revision
- HTTP = port 80
- HTTPS = port 443
- HTTPS uses encryption
- HTTPS is preferred for sensitive data
