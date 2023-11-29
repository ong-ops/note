# Wireshark

- Download: https://www.wireshark.org/download.html
- For Linux, `apt install wireshark`

## Collection Method

- Network Taps
- MAC Floods
- ARP poisoning

## Filtering Operators

- and / &&
- or / ||
- eq / ==
- ne / !=
- gt / >
- lt / <

## Basic Filtering

- `ip.addr == <IP Address>`
- `ip.src == <SRC IP Address and ip.dst == <DST IP Address>`
- `tcp.port eq <Port #> or <Protocol Name>`
- `udp.port eq <Port #> or <Protocol Name>`
- `frame.number == 6`
- `arp.opcode == 1`
- `arp.src.hw_mac == 80:fb:06:f0:45:d7`

## More Practice

- https://wiki.wireshark.org/SampleCaptures#sample-captures
- https://dfirmadness.com/case-001-pcap-analysis/
