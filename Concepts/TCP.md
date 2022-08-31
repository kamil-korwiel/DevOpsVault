# TCP

---
Is a [[Protocol]]  / standard for exchanging data between different devices in a computer network.

```mermaid
sequenceDiagram
Client->>Server: SYN|SEQ.Client
Server->>Client: SYN-ACK|SEQ.Client +1|SEQ Server
Client->>Server: ACK|SEQ.Client +1|SEQ.Server +1
```
`SYN`- synchronize ( Random number   |    Client SYN 842 - Sever SYN 383 )  
`SEQ`- sequence 
`ACK`- acknowledgment  
