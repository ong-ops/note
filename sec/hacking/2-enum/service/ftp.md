# FTP (Port 21)

- **File Transfer Protocol** is used to transfer files over a network but unencrypted any data
  - https://www.ietf.org/rfc/rfc959.txt
- FTP session operates 2 channels
  - A command or the control channel (TCP port 20)
  - A data channel (TCP port 21)
- FTP connections
  - **Active** is the client opens a port and listens. The server is required to actively connect to it
  - **Passive** is the server opens a port and listens (passively) and the client connects to it

## Enumerate

 - Anonymous Login
 - Solaris 2.6/7.0 - IN.FTPD CWD 'Username' Enumeration (https://www.exploit-db.com/exploits/20745)

## Article

- How to Prevent Sniffer Attacks with Encrypted FTP | JSCAPE (https://www.jscape.com/blog/countering-packet-sniffers-using-encrypted-ftp)

## Command

```
ftp <ip>
```
