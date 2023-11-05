# SMTP (Port 25)

- **Simple Mail Transfer Protocol** is utilised to handle the sending of emails and require a protocol pair for receving mail from server (POP/IMAP).
- Using TCP port 25
- SMTP server performs 3 basic functions
  - Verify emails sender through the SMTP server
  - Send the outgoing mail
  - If the outgoing mail cannot be delivered it sends the message back to the sender

## POP, IMAP

- **Post Office Protocol** and **Internet Message Access Protocol** are responsible for the transfer of email between a client and a mail server.
- POP is more simplistic approach of downloading the inbox from the mail server to the client.
- IMAP will synchronise the current inbox with new mail on the server, downloading anything new.

## How does SMTP work?

```
User --> SMTP Server --> The wider Internet --> POP / IMAP Server --> Recipient
```
https://computer.howstuffworks.com/e-mail-messaging/email3.htm

## Enumerate

### Server Details

Use the `auxiliary/scanner/smtp/smtp_version` module in Metasploit to scan a range of IP and determine the version of any mail servers
```
msfconsole
use smtp_version
```

### Users from SMTP

- It has 2 internal commands to reveal a list of valid users
  - VRFY (Confirming the names of valid users)
  - EXPN (Reveals the actual address of user's aliases and lists of e-mail)
- We can do this manually over a `telnet`
- Use the `auxiliary/scanner/smtp/smtp_enum` module in Metasploit
  - Set a host or range of hosts to scan and a wordlist containing usernames to enumerate
```
msfconsole
use smtp_enum
```

### Alternative

- `smtp-user-enum` is performed by inspecting the responses to VRFY, EXPN, RCPT TO commands
