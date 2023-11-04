# Enum4Linux

- Used to Enumerate SMB shares on Windows and Linux
- Wrapper around the tools in the Samba package and extract info from the target pertaining to SMB
- https://github.com/CiscoCXSecurity/enum4linux

## Syntax

- `enum4linux [options] ip`

## Options

- `-U` Get user list
- `-M` Get machine list
- `-N` Get name list dump (different from -U and -M)
- `-S` Get share list
- `-P` Get password policy info
- `-G` Get group and member list
- `-a` all of the above (full basic enumeration)

