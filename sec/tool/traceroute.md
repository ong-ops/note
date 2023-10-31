# Traceroute

## Description

- See every intermediate step between your computer and the resource that you requested
- ICMP protocol

## Syntax

- `traceroute <destination>`  
- Windows traceroute: `tracert`

## Example

- `traceroute tryhackme.com`

```
traceroute: Warning: tryhackme.com has multiple addresses; using 172.67.27.10
traceroute to tryhackme.com (172.67.27.10), 64 hops max, 52 byte packets
 1  192.168.1.1 (192.168.1.1)  11.009 ms  3.374 ms  3.261 ms
 2  100.110.0.1 (100.110.0.1)  17.940 ms  20.688 ms  28.565 ms
 3  10.121.102.246 (10.121.102.246)  9.508 ms
    10.121.102.242 (10.121.102.242)  6.574 ms
    10.121.102.218 (10.121.102.218)  7.972 ms
 4  10.33.44.14 (10.33.44.14)  6.823 ms * *
 5  10.33.45.197 (10.33.45.197)  11.215 ms  15.314 ms  25.300 ms
 6  * 10.33.46.70 (10.33.46.70)  11.817 ms  6.765 ms
 7  * 10.33.46.53 (10.33.46.53)  13.097 ms *
 8  37.85.50.182.static-corp.jastel.co.th.85.50.182.in-addr.arpa (182.50.85.37)  11.402 ms  20.636 ms  15.576 ms
 9  172.67.27.10 (172.67.27.10)  64.839 ms  5.716 ms  6.592 ms
```

## Options

- `-i iface` Specify a network interface to obtain the source IP for outgoing probe packets
- `-T` Use `TCP` SYN for probes
