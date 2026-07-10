# 3. TCP/IP Model

## 1. Definition
The TCP/IP model is the practical networking model used by the internet.

In simple words, it is the rule set that devices follow to communicate over networks.

## 2. Why does this exist?
The TCP/IP model exists because the internet needs a standard way for devices to exchange data.

- It enables global communication.
- It provides a structured way for data to move between systems.
- It allows different devices and vendors to work together.

## 3. Real-life analogy
Think of TCP/IP like an international courier system.

- the address is written
- the package is labeled
- the courier chooses a route
- the receiver confirms delivery

## 4. Real-world IT example
When you open a website:
- the browser uses the application layer
- TCP or UDP handles transport
- IP handles routing
- the network medium carries the data

## 5. TCP/IP layers

| Layer | Main job |
|---|---|
| Application | Supports services like HTTP, DNS, SMTP |
| Transport | Handles end-to-end delivery with TCP or UDP |
| Internet | Handles IP addressing and routing |
| Link | Handles local network access such as Ethernet or Wi-Fi |

## 6. Core concepts

### Application Layer
- Definition: The layer where user services operate.
- Example: Browser, email, DNS.
- Interview point: “What protocols are at the application layer?”
- Memory trick: Application = services.

### Transport Layer
- Definition: The layer that handles delivery between endpoints.
- Example: TCP and UDP.
- Interview point: “Which layer includes TCP and UDP?”
- Memory trick: Transport = delivery.

### Internet Layer
- Definition: The layer that handles logical addressing and routing.
- Example: IP packets and routing tables.
- Interview point: “What does the internet layer do?”
- Memory trick: Internet = IP and routing.

### Link Layer
- Definition: The layer that handles direct connection to a local network.
- Example: Ethernet, Wi-Fi.
- Interview point: “What is the link layer?”
- Memory trick: Link = local connection.

## 7. Packet flow
When you access a webpage:
1. The application creates the request.
2. Transport adds TCP or UDP information.
3. Internet adds IP information.
4. Link layer sends the packet over the local network.
5. Routers forward it across networks.
6. The server responds and the data returns.

## 8. Interview questions
### Beginner
- What is the TCP/IP model?
- What are the four layers?
- What is the purpose of IP?

### Intermediate
- Which layer handles routing?
- Which layer includes TCP and UDP?
- How is TCP/IP different from OSI?

### Short exam-style answer
TCP/IP is the real-world model used by the internet. It has four layers: application, transport, internet, and link. The internet layer manages IP and routing, while the transport layer manages delivery using TCP or UDP.

## 9. Common mistakes
- Treating TCP/IP as the same as OSI.
- Thinking TCP/IP means only TCP.
- Forgetting that IP works at the internet layer.

## 10. Quick revision
- TCP/IP = real internet model
- Application = services
- Transport = delivery
- Internet = IP and routing
- Link = local network access

## 11. Exam summary
TCP/IP is the practical model used in real networks. For interviews, focus on the four layers and the role of IP, TCP, and UDP.
