# Hydra

- A very fast online password cracking
- Perform rapid dictionary attacks against more than 50 protocols (Telnet, RDP, SSH, FTP, HTTP, HTTPS, SMB, Databases, more...)
- https://github.com/vanhauser-thc/thc-hydra
- https://www.kali.org/tools/hydra/

## Syntax

- `hydra [options] [machine IP] [protocol]`
- `hydra -t 4 -l dale -P /usr/share/wordlists/rockyou.txt -vV 10.10.10.6 ftp`

## Options

- `-t 4` Number of parallel connections per target
- `-l [user]` Points to the user who's account you're trying to compromise
- `-P [path to dictionary]` Points to the file containing the list of possible passwords
- `-vV` Very verbose mode

