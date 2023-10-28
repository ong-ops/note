# nmap

## Options

### Scanning  

- `-sT` TCP scan
  - **Default scan without sudo permission**
  - Use full three-way handshake with the target
    - |----- SYN ----->|
    - |<-- SYN/ACK --|
    - |----- ACK ----->|
  - Result status
    - `closed`
      - the server responds reset(RST)
    - `filtered`
      - Packet is dropped by firewall or spoofed with a TCP reset
- `-sS` Syn Half-open/Stealth scan
  - **Default scan for sudo permission**
  - Send back RST after receiving a SYN/ACK (Prevent the server from repeatedly trying to make request)
    - |----- SYN ----->|
    - |<-- SYN/ACK --|
    - |----- RST ----->|
  - Pros
    - Can bypass old IDS (look full three-way handshake)
    - Often not logged by app on open ports because the connection is not fully established
    - Faster than TCP scan
  - Cons
    - Required sudo permission to root user because require to create a raw packet
    - Unstable services are sometimes down
- `-sU` UDP scan
  - Result status
    - `open|filtered`
      - It suspects the port is open or firewalled
      - Very unusual to gets a UDP response (More commonly no response)
    - `closed`
      - the target should response with an ICMP (ping) packet with message port is unreachable
  - Slow > TCP scan
  - Good practice to run with `--top-ports <number>`
    - `nmap -sU --top-ports 20 <target>`
- `-sN` Null scan
- `-sF` FIN scan
- `-sX` Xmas scan

### Scanning - Port

- `-p <port ranges>`  Scan specified ports
- `-p-` Scan all ports

### Scanning - Script

- `--script` Use a script
  - `-sC` == `--script=default`
  - `--script=vuln`

### Detect - OS

- `-O` Check OS

### Detect - Service/Version

- `-sV` Check service/version info on open ports

### Timing and Performance

- `-T<0-5>` Set timing template (higher is faster)

### Output

- `-v` Increase verbosity level
- `-vv` verbosity level 2 (USE THIS)

### Output - File

- `-oA` Save output in the 3 formats
- `-oN` Save output as Normal format
- `-oG` Save output as Grepable format

### MISC

- `-A` Enable to detect OS, version, script scanning, traceroute
