# SMB (Port 445)

- **Server Message Block Protocol** is a client-server communication protocol used for sharing access to files, printers, serial ports and other resources on a network
- Using TCP port 445
```
Client                       Server  
|-------- SMB Requests ------->|  
|<------ SMB Responses --------|
```
- Request-Response protocol transmit multiple messages between the client and server to establish a connection
- Client using NBT, IPX/SPX, NBF
- Use `Kerberos` protocol to authen users against `Active Directory` on Windows domain networks
- Opportunistic locking (OpLocks)
  - Improve file performance
  - Controlling caching of network files by the client
  - Types
    - Batch Locks
      - support DOS batch file execution operation which the file is opened and closed many times in a short period
      - Client ask for OpLock type `batch`
      - Client delays sending the close request and if subsequent open request is given, the 2 requests cancel each other
    - Level-1 OpLocks / Exclusive Locks
      - When app open in `shared mode` a file hosted on SMB server which is not opened by other process/clients
      - The client receives an `exclusive OpLock` from the server
    - Level-2 OpLocks
      - Like Level 1 but allow other client write/read access
    - Filter OpLocks
      - Like Level 2 but prevent sharing-mode violations between file open and lock reception
      - MS advises use only where it is important to allow multiple readers and Level 2 in other circumstances
    - Breaks
      - A break request may be sent from server to client.
      - Informs the client that OpLock is not longer valid

## Command

Enumerate a SMB service on a server
```
enum4linux <options> <ip>
```
- `-U` Get user list
- `-M` Get machine list
- `-N` Get name list dump (Different from -U and -M)
- `-S` Get share list
- `-P` Get password policy info
- `-G` Get group and member list
- `-a` All of the above (Full basic enumeration)
- https://github.com/CiscoCXSecurity/enum4linux

---

Connect to a SMB shared folder
```
smbclient //<ip>/<share>
```
- `-U <name>` Specific the user
- `-p <port>` Specific the port
