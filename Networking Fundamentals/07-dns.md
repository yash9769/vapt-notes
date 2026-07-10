# DNS

## Definition
DNS stands for Domain Name System. It translates human-readable domain names such as google.com into IP addresses that computers use to connect.

## Why it exists
- Humans remember names more easily than long numeric IP addresses.
- It makes the internet easier to use.
- Without DNS, users would need to remember the IP address of every website.

## Simple explanation
DNS is like a phonebook of the internet. Instead of remembering a number, you search for a name.

## Real-life analogy
Think of DNS like a contact list on your phone.
- You type a person’s name.
- The phone finds their number.
- Then you call them.

DNS does the same thing for websites.

## How it works
1. A user types a domain name in the browser.
2. The device sends a DNS query to a DNS server.
3. The DNS server checks its records.
4. It returns the correct IP address.
5. The browser connects to that IP address.

## Important DNS records
- A record: maps a domain to an IPv4 address
- AAAA record: maps a domain to an IPv6 address
- CNAME: points one name to another name
- MX record: mail exchange record for email
- TXT record: stores text information such as SPF or verification data

## Common interview points
- What is DNS?
- Why is DNS needed?
- What is the difference between a domain name and an IP address?
- What is the role of a DNS server?

## Real-world example
When you open youtube.com:
- your device asks a DNS server for the IP address of youtube.com
- DNS returns the address
- your browser connects to the correct server

## Common mistakes
- Confusing DNS with web hosting.
- Thinking DNS stores website content.
- Forgetting that DNS only resolves names to addresses.

## Memory trick
DNS = Domain Name Service
Think: DNS = Phonebook

## Quick revision
- DNS translates names to IP addresses
- It is like a phonebook
- It is used whenever you open a website or send email
