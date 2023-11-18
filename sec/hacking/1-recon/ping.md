# Ping

- Test a connection to a remote resource is possible.
- Using ICMP protocol that works on the Network layer (OSI Model) or Internet layer (TCP/IP Model)
- Ping return IP address of the server hosting a website
- All OS support

## Command

```
ping google.com
```
- `-i wait` Wait seconds between sending each packet
- `-v` Verbose output
- `-c` count

Output
```
PING google.com (172.217.166.142): 56 data bytes
64 bytes from 172.217.166.142: icmp_seq=0 ttl=113 time=26.417 ms
64 bytes from 172.217.166.142: icmp_seq=1 ttl=113 time=28.034 ms
Request timeout for icmp_seq 2
Request timeout for icmp_seq 3
Request timeout for icmp_seq 4
64 bytes from 172.217.166.142: icmp_seq=5 ttl=113 time=39.708 ms
64 bytes from 172.217.166.142: icmp_seq=6 ttl=113 time=36.795 ms
^C
--- google.com ping statistics ---
7 packets transmitted, 4 packets received, 42.9% packet loss
round-trip min/avg/max/stddev = 26.417/32.739/39.708/5.637 ms
```
