# 4. TCP vs UDP

## 1. Definition
TCP and UDP are two transport layer protocols used to send data over a network.

In simple words:
- TCP is reliable and ordered.
- UDP is faster and lightweight.

## 2. Why do they exist?
They exist because different applications need different delivery methods.

- TCP solves the problem of reliable delivery.
- UDP solves the problem of speed and low delay.
- Some applications care more about correctness, while others care more about real-time performance.

## 3. Real-life analogy
- TCP is like a registered courier service that confirms delivery.
- UDP is like a public announcement where speed matters more than confirmation.

## 4. Real-world IT example
- TCP is used for web browsing, email, and file transfer.
- UDP is used for DNS queries, VoIP, online gaming, and live streaming.

## 5. Core concepts

### TCP
- Definition: A connection-oriented protocol that ensures reliable delivery.
- Why it matters: It prevents data loss and maintains order.
- Interview point: “Is TCP reliable?”
- Memory trick: TCP = reliability.

### UDP
- Definition: A connectionless protocol that sends data quickly with less overhead.
- Why it matters: It is ideal for real-time traffic.
- Interview point: “Why is UDP faster?”
- Memory trick: UDP = speed.

### Three-way handshake
- Definition: The process TCP uses to establish a connection.
- Steps: SYN, SYN-ACK, ACK.
- Why it matters: It ensures both sides are ready.
- Interview point: “What is the TCP three-way handshake?”

### Acknowledgment
- Definition: A confirmation that data was received.
- Why it matters: It helps TCP retransmit missing data.
- Interview point: “What is acknowledgment in TCP?”

### Flow control and congestion control
- Definition: Mechanisms that help TCP avoid overwhelming the network or receiver.
- Why it matters: They improve stability and performance.

## 6. Packet flow
### TCP flow
1. Client sends SYN.
2. Server replies with SYN-ACK.
3. Client sends ACK.
4. Connection is established.
5. Data is exchanged.
6. Receiver confirms delivery.

### UDP flow
1. Client sends data.
2. Server receives it.
3. No handshake is required.
4. If a packet is lost, it is not automatically resent.

## 7. Interview questions
### Beginner
- What is TCP?
- What is UDP?
- Which is more reliable?

### Intermediate
- What is the three-way handshake?
- Why is UDP used in live video calls?
- Why is TCP used for web pages and downloads?

### Short exam-style answer
TCP is connection-oriented and reliable, so it is used where accuracy matters. UDP is connectionless and faster, so it is used for real-time applications such as gaming and video calls.

## 8. Common mistakes
- Saying UDP is always better.
- Saying TCP is always better.
- Confusing TCP with IP.

## 9. Quick revision
- TCP = reliable
- UDP = fast
- TCP uses handshake and acknowledgments
- UDP does not guarantee delivery

## 10. Comparison table

| Feature | TCP | UDP |
|---|---|---|
| Reliability | High | Low |
| Connection | Connection-oriented | Connectionless |
| Speed | Slower | Faster |
| Overhead | Higher | Lower |
| Use case | Web, email, file transfer | Streaming, gaming, VoIP |
| Acknowledgment | Yes | No |

## 11. Exam summary
Choose TCP when accuracy matters and UDP when speed matters. In interviews, the most important point is that TCP is reliable while UDP is fast and lightweight.
