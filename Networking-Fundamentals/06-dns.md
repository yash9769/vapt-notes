
# Phase 1 — Networking Fundamentals

![06_dns](../assets/networking/06_dns.png)

# Concept 6: DNS (Domain Name System)

## Definition

DNS converts human-readable domain names into IP addresses.

Example:

```text
google.com

↓

142.250.x.x
```

Humans remember names, while computers communicate using IP addresses.

---

# Why Do We Need DNS?

Without DNS, users would need to memorize IP addresses for every website.

Instead of typing:

```text
140.82.x.x
```

you simply type:

```text
github.com
```

---

# How DNS Works

Suppose you open:

```text
https://github.com
```

The following steps occur:

1. Your browser requests the IP address of GitHub.
2. The DNS server searches for the IP.
3. The DNS server sends the IP address back.
4. Your browser connects to GitHub.

---

# DNS Records

## A Record

Maps a domain to an IPv4 address.

Example:

```text
google.com → 142.250.x.x
```

---

## AAAA Record

Maps a domain to an IPv6 address.

---

## MX Record

Specifies the mail server.

Example:

```text
gmail.com → mail servers
```

---

## CNAME Record

Creates an alias for another domain.

Example:

```text
blog.example.com → example.com
```

---

## NS Record

Specifies the authoritative DNS servers.

---

## TXT Record

Stores text information.

Common uses:

* SPF
* DKIM
* Domain verification

---

# DNS Ports

| Protocol | Port |
| -------- | ---- |
| UDP      | 53   |
| TCP      | 53   |

Usually:

* UDP is used for normal DNS queries.
* TCP is used for large responses and zone transfers.

---

# DNS Tools

Find the IP address:

```bash
nslookup github.com
```

Using dig:

```bash
dig github.com
```

---

# DNS in VAPT

DNS provides valuable reconnaissance information.

Security testers use DNS to:

* Find subdomains.
* Discover mail servers.
* Identify technologies.
* Gather attack-surface information.

Popular tools:

* nslookup
* dig
* subfinder
* amass

---

# DNS Attack Examples

## DNS Spoofing

An attacker tricks a victim into visiting a fake website.

Example:

```text
bank.com

↓

Attacker's server
```

---

## Zone Transfer Misconfiguration

A DNS server accidentally exposes all domain records.

---

# Memory Trick

```text
DNS = Internet Phonebook
```

Just as a phonebook maps names to phone numbers, DNS maps domain names to IP addresses.

---

# Interview Answer

DNS (Domain Name System) translates domain names into IP addresses so that computers can communicate over the internet. It commonly uses port 53 and plays a major role in networking and reconnaissance.
