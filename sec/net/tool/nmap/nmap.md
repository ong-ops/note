# nmap

## Options

### Scanning  

- `-sS` Syn Half-open scan
- `-sT` TCP scan
- `-sU` UDP scan
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

- `sV` Check service/version info on open ports

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
