# nbtstat

- Diagnostic tool for NetBIOS over TCP/IP
- Help troubleshoot NetBIOS name solution problems
- Included in serveral versions of MS
- Allow to
  - Local cache lookup
  - WINS server query
  - Boardcast
  - LMHOSTS lookup
  - Hosts lookup

## Options
 
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
