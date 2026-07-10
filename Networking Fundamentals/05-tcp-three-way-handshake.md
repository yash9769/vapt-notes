# TCP Three-Way Handshake

## Definition
The TCP three-way handshake is the process used by TCP to establish a reliable connection between client and server before data transfer begins.

## Why it exists
- It ensures both sides are ready to communicate.
- It helps avoid sending data to a device that is not listening.
- It sets up the connection state for reliable data transfer.

## Simple explanation
TCP does not start sending data immediately. First, it checks whether the other side is available.

## Steps
1. SYN
   - The client sends a synchronization request to the server.
   - It says: “I want to start a connection.”

2. SYN-ACK
   - The server receives the request.
   - It replies and acknowledges the request.
   - It says: “I received your request and I am ready.”

3. ACK
   - The client sends an acknowledgment back.
   - It says: “I received your reply, and we can start.”

## Diagram
Client -> SYN -> Server
Client <- SYN-ACK <- Server
Client -> ACK -> Server

## Why it is important
- Establishes a connection before data transfer.
- Helps TCP ensure reliability.
- Used in almost every web request.

## Real-world example
When you open a website:
- your browser first starts a TCP connection with the web server.
- once the handshake completes, the browser and server begin exchanging data.

## Interview points
- What is the TCP three-way handshake?
- Why is it called three-way?
- What are SYN, SYN-ACK, and ACK?

## Memory trick
SYN = I want to connect
SYN-ACK = I heard you and I accept
ACK = Okay, let us begin

## Quick revision
- TCP handshake has 3 steps.
- SYN, SYN-ACK, ACK.
- It establishes connection before data transfer.
