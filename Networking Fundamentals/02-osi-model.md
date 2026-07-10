# 2. OSI Model

## 1. Definition
The OSI model is a conceptual model used to explain how data moves through a network.

In simple words, it breaks networking into 7 layers so each layer has a clear job.

## 2. Why does this exist?
The OSI model exists to make networking easier to understand and troubleshoot.

- It creates a standard way to describe communication.
- It helps engineers isolate problems by layer.
- It improves compatibility between different vendors and technologies.

## 3. Real-life analogy
Think of the OSI model like a factory production line.

- one team prepares the product
- another checks quality
- another handles packaging
- another moves it to the delivery point

Each stage has a specific role.

## 4. Real-world IT example
When you browse a website:
- application layer handles the request
- transport layer controls delivery
- network layer chooses the path
- data link and physical layers send the bits over the network

## 5. OSI layers

| Layer | Name | Main responsibility |
|---|---|---|
| 7 | Application | User-facing services like HTTP, DNS, SMTP |
| 6 | Presentation | Formatting, encryption, compression |
| 5 | Session | Managing sessions and connections |
| 4 | Transport | Reliable or fast delivery of data |
| 3 | Network | IP addressing and routing |
| 2 | Data Link | Local delivery using MAC addresses |
| 1 | Physical | Cables, radio waves, electrical signals |

## 6. Core concepts

### Layer 7: Application
- Definition: The layer where network services are used by applications.
- Interview point: “What layer is HTTP on?”
- Memory trick: Application = services.

### Layer 6: Presentation
- Definition: The layer that formats and encrypts data.
- Interview point: “What does the presentation layer do?”
- Memory trick: Presentation = format and secure.

### Layer 5: Session
- Definition: The layer that manages sessions between applications.
- Interview point: “What is the session layer?”
- Memory trick: Session = connection management.

### Layer 4: Transport
- Definition: The layer that controls delivery of data.
- Interview point: “Which layer uses TCP and UDP?”
- Memory trick: Transport = delivery control.

### Layer 3: Network
- Definition: The layer that handles logical addressing and routing.
- Interview point: “Which layer uses IP addresses?”
- Memory trick: Network = routing.

### Layer 2: Data Link
- Definition: The layer that handles local communication between devices.
- Interview point: “What does Layer 2 do?”
- Memory trick: Data Link = local delivery.

### Layer 1: Physical
- Definition: The layer that transmits raw bits over media.
- Interview point: “What happens at the physical layer?”
- Memory trick: Physical = wires and signals.

## 7. Packet flow
When a browser requests a webpage:
1. Application layer creates the request.
2. Presentation layer formats it.
3. Session layer manages the connection.
4. Transport layer prepares the segment.
5. Network layer adds IP information.
6. Data Link layer frames it.
7. Physical layer sends it over the medium.

## 8. Interview questions
### Beginner
- What is the OSI model?
- How many layers are there?
- Which layer handles routing?

### Intermediate
- Which layer uses MAC addresses?
- Which layer is responsible for encryption?
- What is the difference between Layer 2 and Layer 3?

### Short exam-style answer
The OSI model is a 7-layer framework that explains how data moves through a network. Layer 3 handles routing and IP addressing, Layer 4 handles transport, and Layer 1 handles the physical transmission of bits.

## 9. Common mistakes
- Confusing OSI with TCP/IP.
- Memorizing the layers without understanding their purpose.
- Mixing up Application and Transport layers.

## 10. Quick revision
- OSI has 7 layers.
- Layer 3 = routing.
- Layer 4 = transport.
- Layer 1 = physical signals.

## 11. Exam summary
The OSI model is mainly used for learning, teaching, and troubleshooting. In interviews, remember the layer order and the main responsibility of each layer.
