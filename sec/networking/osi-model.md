# OSI Model

## 7 Layers

- Application
  - Networking options to programs running on a computer
- Presentation
  - Translate data to standard format
  - Encryption, Compression, Transform
- Session
  - Unique communication
  - Sync communicate with the session layer of the remote computer
  - Make multiple requests to different endpoints
- Transport
  - Choose the protocol (TCP, UDP, etc...)
  - Divides the transmission into bite-sized pieces (TCP: Segments, UDP: Datagrams)
- Network
  - Locate destination
  - Logical addressing (IP Address)
  - Packet
- Data Link
  - Physical addressing
  - NIC (Network Interface Card)
    - MAC (Media Access Control)
  - Frame
- Physical
  - Convert binary to signal
