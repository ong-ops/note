# NetBIOS (Port 137, 138, 139)

- Network Basic Input/Output System
- Provide services related to the session layer of the OSI model
- Communicate over LAN
- https://en.wikipedia.org/wiki/NetBIOS

## Service

- NetBIOS-NS 
  - **NetBIOS Name Service** is used to register an application using NetBIOS name
  - Using UDP port **137** (TCP is rarely)
  - IPv6 are not supported
  - 16 octets (15 char + 1 char as a Suffix)
    - Suffix describes the service or name record type (host, master browser, domain controller, other services)
  - Function:
    - `Add name` Registers a NetBIOS name
    - `Add group name` Registers a NetBIOS group name
    - `Delete name` Un-register a NetBIOS name or group name
    - `Find name` Looks up a NetBIOS name on the network
- NetBIOS-DGM
  - **NetBIOS Datagram distribution service** is a connectionless and application responsible for error detection and recovery
  - Using UDP port **138**
  - Function:
    - `Send Datagram` Send a datagram to a remote NetBIOS name
    - `Send Boardcast Datagram` Send a datagram to all NetBIOS names on the network
    - `Receive Datagram` Wait for a packet to arrive from a Send Datagram
    - `Receive Boardcase Datagram` Wait for a packet to arrive from a Send Boardcast Datagram
- NetBIOS-SSN
  - **NetBIOS Session service** is a connection-oriented and allow messages to span multiple packets and provide error detection and recovery
  - Using TCP port **139**
  - Function:
    - `Call` Opens a session to a remote NetBIOS name
    - `Listen` Listens for attempts to open a session to a NetBIOS name
    - `Hang Up` Close a session
    - `Send` Sends a packet to the computer on the other end of a session
    - `Send No Ack` like `Send`, but doesn't require an acknowledgement
    - `Receive` Wait for a packet to arrive from a Send on the other end of a session

## Node type

- Resolve NetBIOS names to IP
  - `B-node` 0x01 Boardcast
  - `P-node` 0x02 Peer (WINS only)
  - `M-node` 0x04 Mixed (boardcast, then WINS)
  - `H-node` 0x08 Hybrid (WINS, then boardcast)
- display node type by `ipconfig /all`
- Computer Registry may be configured to display `unknown` for the node type

## Suffix

- Alt called the NetBIOS End Character (endchar)
- 16th char of a NetBIOS names
- Indicate service type for the registered name
- number of record type is limited to 255
- For unique name
  - `00` Workstation service (workstation name)
  - `03` Windows Messenger service
  - `06` Remove Access Service
  - `20` File Service (Host Record)
  - `21` Remove Access Service client
  - `1B` Domain master browser - primary domain controller for a domain
  - `1D` Master browser
- For group name
  - `00` Workstation service (workgroup/domain name)
  - `1C` Domain controller for a domain (group record with up to 25 IP)
  - `1E` Browser Service Elections

# NetBIOS Frames - (NBF)

- Used MS networking in 1990s
- A non-routeable network and transport level protocol
  - Only well-suited for small to medium-sized networks
  - Only used to communicate with devices in the same boardcast domain
  - It can use `bridges` to communicate with network segments connected to each other
- IEEE 802.2 LLC mode 1 provides the NetBIOS/NetBEUI name service and datagram service
- IEEE 802.2 LLC mode 2 provides the NetBIOS/NetBEUI session service (virtual circuit)
- Less configure than TCP/IP
- NetBIOS/NetBEUI services must be implemented atop other protocols (IPX, TCP/IP)

# Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX)

- Networking protocol initially on networks using the Novell NetWare OS
- Widely used on networks deploying MS Windows LANS
- Designed for LANs
- IPX is a network layer
  - Similar to IP
- SPX is a transport layer
  - Provides Connection-Oriented services between 2 nodes on the network
  - Used by client-server app
  - Used `NAKs` for confirm acknowledgement like TCP `ACK`

# NetBIOS over TCP/IP (NBT, NetBT)

- Networking protocol allows legacy computer app on the NetBIOS API to used on modern TCP/IP

## Command

Diagnostic tool for NetBIOS over TCP/IP
```
nbtstat
```
- Help troubleshoot NetBIOS name solution problems
- Included in serveral versions of MS
- Allow to
  - Local cache lookup
  - WINS server query
  - Boardcast
  - LMHOSTS lookup
  - Hosts lookup
- Options
  - `nbtstat -a <Remote name>` Performs a NetBIOS adapter status on computer name
    - Returns the local NetBIOS name table for that computer and MAC address of the adapter card
  - `nbtstat -A <IP>` Performs the same function using a target IP
  - `-c` Displays the contents of the NetBIOS name cache, the table of NetBIOS name and resolved IP
  - `-n` Displays the names registered on the system
  - `-r` Displays the count of all NetBIOS names resolved by boardcast and querying a WINS server
  - `-R` Purge and reload the remote cache name table
  - `-RR` Sends name release packets to WINS and then Refresh
  - `-s` Lists the current NetBIOS sessions and status, including statistics
  - `-S` Lists sessions table with desc IP
