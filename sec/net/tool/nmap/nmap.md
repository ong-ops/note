# nmap

## Options

### Scanning - Type 

- `-sn`
  - ICMP Network scanning
  - Find IP addresses contain active hosts
  - Perform `ping sweep` (send ICMP to each possible IP)
  - Can specified a hypen`-` or CIDR notation
    - `nmap -sn 192.168.0.1-254` or `nmap -sn 192.168.0.0/24`
  - Not to scan any ports
    - Rely on ICMP echo packets
      - Send TCP SYN to port 443
      - Send TCP ACK or TCP SYN if not run as root packet to port 80
    - Or ARP requests on a local network if run with sudo or root user)
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
  - Client send back RST after receiving a SYN/ACK (Prevent the server from repeatedly trying to make request)
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
  - TCP port
  - TCP request sent with **no flag** set (Empty packet)
  - Expect **RST** if the port is closed
- `-sF` FIN scan
  - TCP port
  - TCP request sent with **FIN flag**
  - Expect **RST** if the port is closed
- `-sX` Xmas scan
  - TCP port
  - TCP request sent with **malform packet** (flag sets as PSH, URG, FIN)
  - Expect **RST** if the port is closed
  - If the port is firewalled then result will be `open|filtered`, `closed` or `filtered`
  - If a port is `filtered` with one of these scans because the target responds with an ICMP unreachable packet
- Scan Null, FIN, Xmas
  - it is not always when hosts respond to malformed packet with RST for closed port and don't respond at all for open ports
    - Windows and a lot of Cisco network devices respond with a RST to any malformed TCP packet regardless the port is open or not
  - The goal is firewall evasion to drop the SYN flag (not 100% for modern systems)

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
