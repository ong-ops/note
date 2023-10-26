# Dig

## Description

- Manually query recursive DNS servers
- TTL (second)

## Syntax

`dig <domain> @<dns-server-ip>`

## Example

`dig google.com @1.1.1.1`

```
; <<>> DiG 9.10.6 <<>> google.com @1.1.1.1
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 2783
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;google.com.                    IN      A

;; ANSWER SECTION:
google.com.             147     IN      A       142.251.43.110

;; Query time: 36 msec
;; SERVER: 1.1.1.1#53(1.1.1.1)
;; WHEN: Fri Oct 27 01:49:34 +07 2023
;; MSG SIZE  rcvd: 55
```

## Options

